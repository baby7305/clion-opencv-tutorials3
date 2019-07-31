cmake_minimum_required(VERSION 3.9)
project(clion_opencv_app)

set(CMAKE_CXX_STANDARD 11)

find_package(OpenCV)

include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(clion_opencv_app main.cpp)
target_link_libraries(clion_opencv_app ${OpenCV_LIBS})