cmake_minimum_required(VERSION 3.4.1)

project(Dummy)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# https://doc.magnum.graphics/corrade/corrade-cmake.html#corrade-cmake-subproject

set(WITH_CONTAINERS ON CACHE BOOL "" FORCE)
set(WITH_PLUGINMANAGER OFF CACHE BOOL "" FORCE)
set(WITH_UTILITY ON CACHE BOOL "" FORCE)
set(WITH_TESTSUITE OFF CACHE BOOL "" FORCE)
set(WITH_RC OFF CACHE BOOL "" FORCE)
add_subdirectory(corrade EXCLUDE_FROM_ALL)

# Path where FindCorrade.cmake can be found, adapt as needed
set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/corrade/modules/" ${CMAKE_MODULE_PATH})
find_package(Corrade REQUIRED Utility Containers)

include_directories(corrade/src)
add_library(Dummy SHARED src/dummy.cpp)
if (ANDROID)
    target_link_libraries(Dummy Corrade Corrade::Containers Corrade::Utility android log)
else()
    target_link_libraries(Dummy Corrade Corrade::Containers Corrade::Utility)
endif()
