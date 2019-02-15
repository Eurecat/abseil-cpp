cmake_minimum_required(VERSION 2.8.3)
project(abseil_cpp)

set(CMAKE_CXX_FLAGS "-std=c++11 -fPIC ${CMAKE_CXX_FLAGS}")

find_package(catkin REQUIRED)

set(CMAKE_POSITION_INDEPENDENT_CODE ON)

set( ABSL_PUBLIC_LIBRARIES
    absl_bad_any_cast
    absl_bad_optional_access
    absl_base
    absl_container
    absl_debugging
    absl_dynamic_annotations
    absl_examine_stack
    absl_failure_signal_handler
    absl_hash
    absl_int128
    absl_leak_check
    absl_meta
    absl_optional
    absl_strings
    absl_stack_consumption
    absl_stacktrace
    absl_synchronization
    absl_symbolize
    absl_time
    absl_variant
    absl_utility
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


