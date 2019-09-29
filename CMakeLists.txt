cmake_minimum_required(VERSION 3.13)
project(clion_opencv_tutorials3)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "C:\\opencv-build\\opencv-3.4.7-qt\\install")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(clion_opencv_app main.cpp)
add_executable(estimateF ./shadow/estimateF.cpp)
add_executable(robustmatching ./shadow/robustmatching.cpp)
add_executable(estimateH ./shadow/estimateH.cpp)


target_link_libraries(clion_opencv_app ${OpenCV_LIBS})
target_link_libraries(estimateF ${OpenCV_LIBS})
target_link_libraries(robustmatching ${OpenCV_LIBS})
target_link_libraries(estimateH ${OpenCV_LIBS})


SET(IMAGES ${CMAKE_SOURCE_DIR}/images/church01.jpg
        ${CMAKE_SOURCE_DIR}/images/church02.jpg
        ${CMAKE_SOURCE_DIR}/images/church03.jpg
        ${CMAKE_SOURCE_DIR}/images/parliament1.jpg
        ${CMAKE_SOURCE_DIR}/images/parliament2.jpg
        ${CMAKE_SOURCE_DIR}/images/parliament3.jpg
        ${CMAKE_SOURCE_DIR}/images/cookbook1.bmp
        ${CMAKE_SOURCE_DIR}/images/objects.jpg)
FILE(COPY ${IMAGES} DESTINATION .)
FILE(COPY ${IMAGES} DESTINATION "Debug")
FILE(COPY ${IMAGES} DESTINATION "Release")
