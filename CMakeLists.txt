cmake_minimum_required(VERSION 3.13)
project(clion_opencv_app)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "F:\\opencv4\\mingw-build\\install")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(clion_opencv_app main.cpp)
target_link_libraries(clion_opencv_app ${OpenCV_LIBS})