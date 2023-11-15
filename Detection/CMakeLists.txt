cmake_minimum_required(VERSION 3.1...3.27)

# This is your project statement. You should always list languages;
# Listing the version is nice here since it sets lots of useful variables
project(
  trafic_analyzer
  VERSION 1.0
  LANGUAGES CXX)
  set(CMAKE_CXX_STANDARD 14)
  set(CMAKE_CXX_STANDARD_REQUIRED ON)
  set(CMAKE_CXX_EXTENSIONS OFF)

find_package( OpenCV REQUIRED )
find_package(OpenCL REQUIRED)

include_directories( ${OpenCV_INCLUDE_DIRS} )

add_executable(trafic_analyzer src/main.cpp)

target_link_libraries(trafic_analyzer 
  ${OpenCV_LIBS}
  # Add other required OpenCV libraries here if needed, for example:
   opencv_core
   opencv_highgui
   opencv_imgproc
   OpenCL::OpenCL
)