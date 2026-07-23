find_package(GTest CONFIG REQUIRED)

add_executable(glftkittests "${CMAKE_CURRENT_SOURCE_DIR}/test_main.cpp")

target_link_libraries(glftkittests 
    PRIVATE 
        GTest::gtest_main   # Automatically provides a standard main() entry point
        GTest::gtest        # The core GoogleTest library
        glftkitlib
)

target_include_directories(glftkittests PRIVATE ../src)

add_test(NAME glftkittests COMMAND glftkittests)