cmake_minimum_required(VERSION 2.4.6)
include($ENV{ROS_ROOT}/core/rosbuild/rosbuild.cmake)

rosbuild_init()

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)

set(PROJECTED_SRC src/library.cc)
rosbuild_add_library(${PROJECT_NAME} ${PROJECTED_SRC})

rosbuild_add_executable(test_executable src/main.cc)
target_link_libraries(test_executable ${PROJECT_NAME})
