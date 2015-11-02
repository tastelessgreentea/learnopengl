cmake_minimum_required(VERSION 2.6)

set(project_name opengl)

project(${project_name})

include_directories(${CMAKE_SOURCE_DIR}/src/)
link_directories(${CMAKE_SOURCE_DIR}/src/)

include_directories(${CMAKE_SOURCE_DIR}/external/include/)

find_package(GLEW REQUIRED)
if (GLEW_FOUND)
   include_directories(${GLEW_INCLUDE_DIRS})
   link_libraries(${GLEW_LIBRARIES})
endif()

find_package(OpenGL REQUIRED)
include_directories(${OpenGL_INCLUDE_DIRS})
link_directories(${OpenGL_LIBRARY_DIRS})
add_definitions(${OpenGL_DEFINITIONS})
link_libraries(${OPENGL_LIBRARIES})

find_package(PkgConfig REQUIRED)
pkg_search_module(GLFW REQUIRED glfw3)
include_directories(${GLFW_INCLUDE_DIRS})
link_libraries(${GLFW_LIBRARIES})
link_directories(${GLFW_LIBRARY_DIRS})

add_subdirectory(src)