include(FetchContent)

set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)

FetchContent_Declare(
    googletest
    GIT_REPOSITORY https://github.com/google/googletest.git
    GIT_TAG v1.18.0
)

FetchContent_MakeAvailable(googletest)

add_executable(MathLibUnitTests math_library_tests.cpp)

target_link_libraries(MathLibUnitTests PRIVATE
    GTest::gtest_main
    math_library
)

add_test(NAME math_library_gtests COMMAND MathLibUnitTests)