cmake_minimum_required( VERSION 2.8 )

project( ceres_curve_fitting )

set(CMAKE_CXX_FLAGS "-std=c++11" )
set(CERES_DIRS /usr/local/ceres/lib/cmake/Ceres )
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${Ceres_DIR})

find_package( OpenCV REQUIRED )
find_package( Ceres REQUIRED )


include_directories( ${OpenCV_INCLUDE_DIRS} )
include_directories( ${CERES_INCLUDE_DIRS} )

link_directories(${CERES_LIBRARY_DIRS})
add_executable(  main main.cpp )
target_link_libraries( main ${OpenCV_LIBRARIES} )
target_link_libraries( main ${CERES_LIBRARIES})




