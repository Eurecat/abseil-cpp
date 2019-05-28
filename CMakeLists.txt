cmake_minimum_required(VERSION 3.5)
project(abseil_cpp)

set(CMAKE_CXX_FLAGS "-std=c++11 -fPIC ${CMAKE_CXX_FLAGS}")

find_package(catkin REQUIRED)

set(CMAKE_POSITION_INDEPENDENT_CODE ON)

set( ABSL_PUBLIC_LIBRARIES
    absl::base
    absl::algorithm
    absl::debugging
    absl::flat_hash_map
    absl::memory
    absl::meta
    absl::numeric
    absl::strings
    absl::synchronization
    absl::time
    absl::utility
)

catkin_package(
   INCLUDE_DIRS ./abseil_cpp
   LIBRARIES ${ABSL_PUBLIC_LIBRARIES}
)

add_subdirectory(abseil_cpp)


#############
## Install ##
#############

# all install targets should use catkin DESTINATION variables
# See http://ros.org/doc/api/catkin/html/adv_user_guide/variables.html


## Mark cpp header files for installation
install(DIRECTORY ./abseil_cpp/absl/
    DESTINATION ${CATKIN_GLOBAL_INCLUDE_DESTINATION}/absl
    FILES_MATCHING PATTERN "*.h"
    PATTERN ".svn" EXCLUDE
 )

install(DIRECTORY ./abseil_cpp/absl/
    DESTINATION ${CATKIN_GLOBAL_INCLUDE_DESTINATION}/absl
    FILES_MATCHING PATTERN "*.inc"
 )

