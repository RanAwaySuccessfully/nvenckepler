cmake_minimum_required(VERSION 3.28...3.30)

find_package(FFnvcodec 11 REQUIRED)

add_executable(${CMAKE_PROJECT_NAME}-test)

target_sources(${CMAKE_PROJECT_NAME}-test PRIVATE tester.cpp)
target_link_libraries(${CMAKE_PROJECT_NAME}-test PUBLIC FFnvcodec::FFnvcodec)

set_target_properties_plugin(${CMAKE_PROJECT_NAME}-test PROPERTIES FOLDER plugins/${CMAKE_PROJECT_NAME})
