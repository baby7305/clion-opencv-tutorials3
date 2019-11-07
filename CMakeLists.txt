cmake_minimum_required(VERSION 3.13)
project(clion_opencv_tutorials3)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "C:\\opencv-build\\opencv-3.4.7-qt\\install")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})
 
add_executable(clion_opencv_app main.cpp)
add_executable( tracker ./tracking/tracker.cpp)
add_executable( flow ./tracking/flow.cpp)


target_link_libraries(clion_opencv_app ${OpenCV_LIBS})
target_link_libraries( tracker ${OpenCV_LIBS})
target_link_libraries( flow ${OpenCV_LIBS})


# copy required images to every directory with executable
SET(IMAGES ${CMAKE_SOURCE_DIR}/images/bike.avi)
FILE(COPY ${IMAGES} DESTINATION .)
FILE(COPY ${IMAGES} DESTINATION "Debug")
FILE(COPY ${IMAGES} DESTINATION "Release")
FILE(COPY ${CMAKE_SOURCE_DIR}/images/goose/ DESTINATION ./goose/)
FILE(COPY ${CMAKE_SOURCE_DIR}/images/goose/ DESTINATION "Debug/goose/")
FILE(COPY ${CMAKE_SOURCE_DIR}/images/goose/ DESTINATION "Release/goose/")
