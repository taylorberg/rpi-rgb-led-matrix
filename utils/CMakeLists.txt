find_package(PkgConfig)

if (PkgConfig_FOUND)
    pkg_check_modules(GraphicsMagick++ IMPORTED_TARGET GraphicsMagick++)

    pkg_check_modules(libavcodec IMPORTED_TARGET libavcodec)
    pkg_check_modules(libavformat IMPORTED_TARGET libavformat)
    pkg_check_modules(libswscale IMPORTED_TARGET libswscale)
    pkg_check_modules(libavutil IMPORTED_TARGET libavutil)

    if (TARGET PkgConfig::GraphicsMagick++)
        add_executable(led-image-viewer led-image-viewer.cc)
        target_link_libraries(led-image-viewer rgb-matrix PkgConfig::GraphicsMagick++)
    endif ()

    if (TARGET PkgConfig::libavcodec
            AND TARGET PkgConfig::libavformat
            AND TARGET PkgConfig::libswscale
            AND TARGET PkgConfig::libavutil)
        add_executable(video-viewer video-viewer.cc)
        target_link_libraries(video-viewer
                rgb-matrix
                PkgConfig::libavcodec
                PkgConfig::libavformat
                PkgConfig::libswscale
                PkgConfig::libavutil)
    endif ()
endif ()

add_executable(text-scroller text-scroller.cc)
target_link_libraries(text-scroller rgb-matrix)