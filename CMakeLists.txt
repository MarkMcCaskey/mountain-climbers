cmake_minimum_required(VERSION 3.5) # I think

project(mountain_climbers C CXX)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)


## Files

file(GLOB_RECURSE sources src/*.cpp src/*.h)
file(GLOB_RECURSE data    resources/*)

add_executable(mountain_climbers ${sources} ${data})

target_compile_options(mountain_climbers PUBLIC -std=c++17 -Wall)

target_include_directories(mountain_climbers PUBLIC src/inc/)


file(COPY ${data} DESTINATION resources)


#install(TARGETS mountain_climbers DESTINATION mountain_climbers_destination)

#install(DIRECTORY resources DESTINATION mountain_climbers_destination)

set(CPACK_PACKAGE_NAME "mountain_climbers")
set(CPACK_PACKAGE_VERSION "1.0.0")

set(CPACK_MONOLITHIC_INSTALL 1)

include(CPack)
