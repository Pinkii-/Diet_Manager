cmake_minimum_required(VERSION 3.5)
project(Diet_Manager)
set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -std=c++11 -fopenmp -lGL -lGLU")

set(SOURCE_FILES main.cpp TextInput.cpp TextInput.h InterfaceList.cpp InterfaceList.h Button.cpp Button.h Inputs.cpp Inputs.h Chart.cpp Chart.h Interface.cpp Interface.h InterfaceSet.cpp InterfaceSet.h CheckBox.cpp CheckBox.h Settings.hpp State.cpp State.hpp Planer.cpp Planer.hpp)
set(EXECUTABLE_NAME "Diet_Manager")
add_executable(${EXECUTABLE_NAME} ${SOURCE_FILES})

# Detect and add SFML
set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules" ${CMAKE_MODULE_PATH})
#Find any version 2.X of SFML
#See the FindSFML.cmake file for additional details and instructions
find_package(SFML 2 REQUIRED system window graphics network audio)
if(SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(${EXECUTABLE_NAME} ${SFML_LIBRARIES})
endif()


