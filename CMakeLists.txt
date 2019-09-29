cmake_minimum_required(VERSION 3.13)
project(clion_opencv_tutorials3)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "C:\\opencv-build\\opencv-3.4.7-qt\\install")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(clion_opencv_app main.cpp)
add_executable(contours ./collect/contours.cpp)
add_executable(blobs ./collect/blobs.cpp)


target_link_libraries(clion_opencv_app ${OpenCV_LIBS})
target_link_libraries(contours ${OpenCV_LIBS})
target_link_libraries(blobs ${OpenCV_LIBS})


SET(IMAGES ${CMAKE_SOURCE_DIR}/images/group.jpg
        ${CMAKE_SOURCE_DIR}/images/binaryGroup.bmp
        ${CMAKE_SOURCE_DIR}/images/mser.bmp
        ${CMAKE_SOURCE_DIR}/images/road.jpg
        ${CMAKE_SOURCE_DIR}/images/chariot.jpg)
FILE(COPY ${IMAGES} DESTINATION .)
FILE(COPY ${IMAGES} DESTINATION "Debug")
FILE(COPY ${IMAGES} DESTINATION "Release")
