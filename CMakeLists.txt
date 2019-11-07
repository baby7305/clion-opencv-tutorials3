cmake_minimum_required(VERSION 3.13)
project(clion_opencv_tutorials3)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "C:\\opencv-build\\opencv-3.4.7-qt\\install")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(clion_opencv_app main.cpp)
add_executable( recognizeFace ./example/recognizeFace.cpp)
add_executable( detectObjects ./example/detectObjects.cpp)
add_executable( trainSVM ./example/trainSVM.cpp)


target_link_libraries(clion_opencv_app ${OpenCV_LIBS})
target_link_libraries( recognizeFace ${OpenCV_LIBS})
target_link_libraries( detectObjects ${OpenCV_LIBS})
target_link_libraries( trainSVM ${OpenCV_LIBS})


# copy required images to every directory with executable
SET(IMAGES ${CMAKE_SOURCE_DIR}/images/girl.jpg
        ${CMAKE_SOURCE_DIR}/images/face0_1.png
        ${CMAKE_SOURCE_DIR}/images/face0_2.png
        ${CMAKE_SOURCE_DIR}/images/face1_1.png
        ${CMAKE_SOURCE_DIR}/images/face1_2.png
        ${CMAKE_SOURCE_DIR}/images/person.jpg
        )
FILE(COPY ${IMAGES} DESTINATION .)
FILE(COPY ${IMAGES} DESTINATION "Debug")
FILE(COPY ${IMAGES} DESTINATION "Release")
FILE(COPY ${CMAKE_SOURCE_DIR}/images/stopSamples/ DESTINATION ./stopSamples/)
FILE(COPY ${CMAKE_SOURCE_DIR}/images/stopSamples/ DESTINATION "Debug/stopSamples/")
FILE(COPY ${CMAKE_SOURCE_DIR}/images/stopSamples/ DESTINATION "Release/stopSamples/")
