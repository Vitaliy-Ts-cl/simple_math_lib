add_subdirectory(math_lib)

add_executable(MathLibExample main.cpp)
target_link_libraries(MathLibExample PRIVATE math_library)
