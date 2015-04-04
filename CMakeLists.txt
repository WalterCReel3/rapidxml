CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
# SET(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/CMakeModules)

PROJECT(RapidXML CXX)

set(CMAKE_CXX_FLAGS "-Wall -Werror -std=c++11")

find_program(MEMORYCHECK_COMMAND valgrind)
set(MEMORYCHECK_COMMAND_OPTIONS "--trace-children=yes --leak-check=full")

#add extra search paths for libraries and includes
SET(INCLUDE_INSTALL_DIR "${CMAKE_INSTALL_PREFIX}/include" CACHE PATH "The directory the headers are installed in")
SET(LIB_INSTALL_DIR "${CMAKE_INSTALL_PREFIX}/lib" CACHE STRING "Directory where lib will install")
SET(DOC_INSTALL_DIR "${CMAKE_INSTALL_PREFIX}/share/doc/${PROJECT_NAME}" CACHE PATH "Path to the documentation")

include_directories(${CMAKE_SOURCE_DIR}/include)

enable_testing()

add_subdirectory(test)

install(DIRECTORY include/rapidxml
	DESTINATION "${INCLUDE_INSTALL_DIR}")

