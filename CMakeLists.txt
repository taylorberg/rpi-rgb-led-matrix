cmake_minimum_required(VERSION 3.16.3)

project(rpi-rgb-led-matrix LANGUAGES C CXX)

if (BUILD_SHARED_LIBRARY)
    add_library(rgb-matrix SHARED)
else ()
    add_library(rgb-matrix STATIC)
endif ()

target_include_directories(rgb-matrix PUBLIC include lib)

target_sources(rgb-matrix PRIVATE
        lib/bdf-font.cc
        lib/content-streamer.cc
        lib/framebuffer.cc
        lib/framebuffer-internal.h
        lib/gpio.cc
        lib/gpio.h
        lib/gpio-bits.h
        lib/graphics.cc
        lib/hardware-mapping.c
        lib/hardware-mapping.h
        lib/led-matrix-c.cc
        lib/led-matrix.cc
        lib/multiplex-mappers.cc
        lib/multiplex-mappers-internal.h
        lib/options-initialize.cc
        lib/pixel-mapper.cc
        lib/thread.cc
        lib/utf8-internal.h

        include/canvas.h
        include/content-streamer.h
        include/graphics.h
        include/led-matrix-c.h
        include/led-matrix.h
        include/pixel-mapper.h
        include/thread.h
        include/threaded-canvas-manipulator.h)

if (BUILD_CSHARP_BINDING)
    enable_language(CSharp)
    add_subdirectory(bindings/c\#)
endif ()

if (BUILD_PYTHON_BINDING)
    # TODO: Figure this out
    #add_subdirectory(bindings/python)
endif ()

add_subdirectory(utils)
add_subdirectory(examples-api-use)
