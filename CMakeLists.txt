cmake_minimum_required(VERSION 3.13)
project(clion_opencv_tutorials3)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "C:\\opencv-vs-build\\opencv-3.4.7\\opencv\\build")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(clion_opencv_tutorials3 main.cpp)


target_link_libraries(clion_opencv_tutorials3 ${OpenCV_LIBS})

