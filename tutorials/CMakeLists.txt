cmake_minimum_required(VERSION 3.20)
project(tutorials)

# 设置 C++ 标准
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
# set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)
# CMAKE_BINARY_DIR: /home/dsg/zed_ws/src/zed-ros-examples/tutorials/build
message(STATUS "CMAKE_BINARY_DIR: " ${CMAKE_BINARY_DIR})
message(STATUS "PROJECT_SOURCE_DIR: " ${PROJECT_SOURCE_DIR})

add_subdirectory("zed_depth_sub_tutorial")
add_subdirectory("zed_obj_det_sub_tutorial")
add_subdirectory("zed_sensors_sub_tutorial")
add_subdirectory("zed_tracking_sub_tutorial")
add_subdirectory("zed_video_sub_tutorial")
