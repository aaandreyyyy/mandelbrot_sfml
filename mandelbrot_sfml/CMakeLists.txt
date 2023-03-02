cmake_minimum_required(VERSION 3.14)
project(mandelbrot_sfml)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++23")

set(SOURCE_FILES main.cpp)
add_executable(mandelbrot_sfml ${SOURCE_FILES})
include_directories(/usr/local/include)
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})
target_link_libraries(mandelbrot_sfml ${OpenCV_LIBS})

find_package(SFML 2.5 COMPONENTS system window graphics network audio REQUIRED)
include_directories(${SFML_INCLUDE_DIRS})
target_link_libraries(mandelbrot_sfml sfml-system sfml-window sfml-graphics sfml-audio sfml-network)