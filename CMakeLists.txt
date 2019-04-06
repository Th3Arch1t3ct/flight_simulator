cmake_minimum_required (VERSION 2.6)
project (FlightSim)

set(FightSim_VERSION_MAJOR 1)
set(FightSim_VERSION_MINOR 0)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/../lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/../lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/../bin)

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)

include_directories(include ${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS} )

file(GLOB SOURCES "src/*.cpp")

add_executable(flightSim ${SOURCES})
target_link_libraries(flightSim ${OPENGL_LIBRARIES} ${GLUT_LIBRARY} )
