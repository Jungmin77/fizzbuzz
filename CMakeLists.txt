make_minimum_required(VERSION 3.12) # version can be different

project(FizzBuzz_project) #name of your project

enable_testing() #to  discover tests in test explorer 

add_library(FizzBuzz hiker.c)

add_subdirectory(googletest) # add googletest subdirectory

include_directories(googletest/include) # this is so we can #include <gtest/gtest.h>

add_executable(mytests hiker.tests.cpp) # add this executable

target_link_libraries(mytests PRIVATE FizzBuzz gtest) # link google test to this executable

include(GoogleTest)
gtest_discover_tests(mytests) # discovers tests by asking the compiled test executable to enumerate its tests