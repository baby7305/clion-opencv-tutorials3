cmake_minimum_required(VERSION 3.13)
project(clion_opencv_tutorials3)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "C:\\opencv-build\\opencv-3.4.7-qt\\install")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(clion_opencv_app main.cpp)
add_executable(patches ./match/patches.cpp)
add_executable(matcher ./match/matcher.cpp)
add_executable(binaryDescriptors ./match/binaryDescriptors.cpp)


target_link_libraries(clion_opencv_app ${OpenCV_LIBS})
target_link_libraries(patches ${OpenCV_LIBS})
target_link_libraries(matcher ${OpenCV_LIBS})
target_link_libraries(binaryDescriptors ${OpenCV_LIBS})


SET(IMAGES ${CMAKE_SOURCE_DIR}/images/church01.jpg
        ${CMAKE_SOURCE_DIR}/images/church02.jpg
        ${CMAKE_SOURCE_DIR}/images/church03.jpg)
FILE(COPY ${IMAGES} DESTINATION .)
FILE(COPY ${IMAGES} DESTINATION "Debug")
FILE(COPY ${IMAGES} DESTINATION "Release")
