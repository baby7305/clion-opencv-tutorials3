cmake_minimum_required(VERSION 3.13)
project(clion_opencv_tutorials3)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "C:\\opencv-build\\opencv-3.4.7-qt\\install")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(clion_opencv_app main.cpp)
add_executable(calibrate ./threeDimensional/calibrate.cpp ./threeDimensional/CameraCalibrator.cpp)


target_link_libraries(clion_opencv_app ${OpenCV_LIBS})
target_link_libraries(calibrate ${OpenCV_LIBS})


SET(IMAGES ${CMAKE_SOURCE_DIR}/images/bench2.jpg
        ${CMAKE_SOURCE_DIR}/images/soup1.jpg
        ${CMAKE_SOURCE_DIR}/images/soup2.jpg
        ${CMAKE_SOURCE_DIR}/images/brebeuf1.jpg
        ${CMAKE_SOURCE_DIR}/images/brebeuf2.jpg
        calib.xml)
FILE(COPY ${IMAGES} DESTINATION .)
FILE(COPY ${IMAGES} DESTINATION "Debug")
FILE(COPY ${IMAGES} DESTINATION "Release")
FILE(COPY ${CMAKE_SOURCE_DIR}/images/chessboards/ DESTINATION ./chessboards/)
FILE(COPY ${CMAKE_SOURCE_DIR}/images/chessboards/ DESTINATION "Debug/chessboards/")
FILE(COPY ${CMAKE_SOURCE_DIR}/images/chessboards/ DESTINATION "Release/chessboards/")
