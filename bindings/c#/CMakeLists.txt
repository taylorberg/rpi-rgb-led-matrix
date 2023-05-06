if (BUILD_SHARED_LIBRARY)
    add_library(rgb-matrix-csharp SHARED)
else ()
    add_library(rgb-matrix-csharp STATIC)
endif ()

target_sources(RGBLedCanvas.cs RGBLedFont.cs RGBLedMatrix.cs)

add_subdirectory(examples)