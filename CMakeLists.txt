cmake_minimum_required(VERSION 3.13)
project(clion_opencv_tutorials3)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR "C:\\opencv-build\\opencv-3.4.7-qt\\install")
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(clion_opencv_app main.cpp)
add_executable(histograms ./histogram/histograms.cpp)
add_executable(contentfinder ./histogram/contentfinder.cpp)
add_executable(finder ./histogram/finder.cpp)
add_executable(retrieve ./histogram/retrieve.cpp)
add_executable(integral ./histogram/integral.cpp)
add_executable(tracking ./histogram/tracking.cpp)


target_link_libraries(clion_opencv_app ${OpenCV_LIBS})
target_link_libraries(histograms ${OpenCV_LIBS})
target_link_libraries(contentfinder ${OpenCV_LIBS})
target_link_libraries(finder ${OpenCV_LIBS})
target_link_libraries(retrieve ${OpenCV_LIBS})
target_link_libraries(integral ${OpenCV_LIBS})
target_link_libraries(tracking ${OpenCV_LIBS})


SET(IMAGES ${CMAKE_SOURCE_DIR}/images/group.jpg
        ${CMAKE_SOURCE_DIR}/images/waves.jpg
        ${CMAKE_SOURCE_DIR}/images/dog.jpg
        ${CMAKE_SOURCE_DIR}/images/baboon01.jpg
        ${CMAKE_SOURCE_DIR}/images/baboon02.jpg
        ${CMAKE_SOURCE_DIR}/images/beach.jpg
        ${CMAKE_SOURCE_DIR}/images/bear.jpg
        ${CMAKE_SOURCE_DIR}/images/lake.jpg
        ${CMAKE_SOURCE_DIR}/images/moose.jpg
        ${CMAKE_SOURCE_DIR}/images/polar.jpg
        ${CMAKE_SOURCE_DIR}/images/marais.jpg
        ${CMAKE_SOURCE_DIR}/images/fundy.jpg
        ${CMAKE_SOURCE_DIR}/images/book.jpg
        ${CMAKE_SOURCE_DIR}/images/bike55.bmp
        ${CMAKE_SOURCE_DIR}/images/bike65.bmp)
FILE(COPY ${IMAGES} DESTINATION .)
FILE(COPY ${IMAGES} DESTINATION "Debug")
FILE(COPY ${IMAGES} DESTINATION "Release")
