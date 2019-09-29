cmake_minimum_required(VERSION 3.13)
project(clion_opencv_tutorials3)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "C:\\opencv-build\\opencv-3.4.7-qt\\install")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(clion_opencv_app main.cpp)
add_executable(derivatives ./filter/derivatives.cpp)
add_executable(filters ./filter/filters.cpp)


target_link_libraries(clion_opencv_app ${OpenCV_LIBS})
target_link_libraries(derivatives ${OpenCV_LIBS})
target_link_libraries(filters ${OpenCV_LIBS})


SET(IMAGES ${CMAKE_SOURCE_DIR}/images/boldt.jpg ${CMAKE_SOURCE_DIR}/images/salted.bmp)
FILE(COPY ${IMAGES} DESTINATION .)
FILE(COPY ${IMAGES} DESTINATION "Debug")
FILE(COPY ${IMAGES} DESTINATION "Release")
