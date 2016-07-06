cmake_minimum_required(VERSION 2.8)
project( FlannMatcherSIFT )

FIND_PACKAGE(Boost COMPONENTS filesystem system REQUIRED)
IF (Boost_FOUND)
	INCLUDE_DIRECTORIES(${Boost_INCLUDE_DIR})
	link_directories(${Boost_LIBRARY_DIR})
	ADD_DEFINITIONS( "-DHAS_BOOST" )
ENDIF()

find_package( OpenCV )
include_directories( ${OpenCV_INCLUDE_DIRS} )

add_executable( FlannMatcherSIFT FlannMatcherSIFT.cpp )
target_link_libraries( FlannMatcherSIFT ${OpenCV_LIBS} )
target_link_libraries( FlannMatcherSIFT ${Boost_LIBRARIES})
