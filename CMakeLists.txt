cmake_minimum_required(VERSION 2.8)
project( FlannMatcherSIFT )
find_package( OpenCV )
include_directories( ${OpenCV_INCLUDE_DIRS} )

set(Boost_INCLUDE_DIR /usr/local/Cellar/boost/1.60.0_2/include)
set(Boost_LIBRARY_DIR /usr/local/Cellar/boost/1.60.0_2/lib)
SET(liblist boost_program_options)
find_package(Boost COMPONENTS system filesystem REQUIRED)
include_directories(${Boost_INCLUDE_DIR})
link_directories(${Boost_LIBRARY_DIR})


add_executable( FlannMatcherSIFT FlannMatcherSIFT.cpp )
target_link_libraries( FlannMatcherSIFT ${OpenCV_LIBS} )