cmake_minimum_required(VERSION 3.10)

if(NOT TARGET Basic)
  # set the project name
  project(HelloProjTest)
  find_package(HelloProj)
  enable_testing()
endif()

add_executable(test_hello test-hello.cpp)
target_link_libraries(test_hello PRIVATE Basic)
add_test(NAME test_hello COMMAND test_hello)

add_executable(test_version test-version.cpp)
target_link_libraries(test_version PRIVATE Basic)
add_test(NAME test_version COMMAND test_version)