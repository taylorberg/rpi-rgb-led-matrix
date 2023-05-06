add_executable(font-example-csharp font-example.cs)
target_link_libraries(font-example-csharp rgb-matrix-csharp)

add_executable(matrix-rain-csharp matrix-rain.cs)
target_link_libraries(matrix-rain-csharp rgb-matrix-csharp)

add_executable(minimal-example-csharp minimal-example.cs)
target_link_libraries(minimal-example-csharp rgb-matrix-csharp)

add_executable(pulsing-brightness-csharp pulsing-brightness.cs)
target_link_libraries(pulsing-brightness-csharp rgb-matrix-csharp)