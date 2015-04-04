project(test)

add_executable(test_simple simple.cpp)
add_test(NAME test_simple COMMAND test_simple WORKING_DIRECTORY ${TEST_DIRECTORY})
