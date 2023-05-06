add_executable(c-example c-example.c)
target_link_libraries(c-example rgb-matrix)

add_executable(clock clock.cc)
target_link_libraries(clock rgb-matrix)

add_executable(demo-main demo-main.cc)
target_link_libraries(demo-main rgb-matrix)

add_executable(input-example input-example.cc)
target_link_libraries(input-example rgb-matrix)

add_executable(ledcat ledcat.cc)
target_link_libraries(ledcat rgb-matrix)

add_executable(minimal-example minimal-example.cc)
target_link_libraries(minimal-example rgb-matrix)

add_executable(pixel-mover pixel-mover.cc)
target_link_libraries(pixel-mover rgb-matrix)

add_executable(scrolling-text-example scrolling-text-example.cc)
target_link_libraries(scrolling-text-example rgb-matrix)

add_executable(text-example text-example.cc)
target_link_libraries(text-example rgb-matrix)