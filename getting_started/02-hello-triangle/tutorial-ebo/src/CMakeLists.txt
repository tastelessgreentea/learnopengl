set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(${project_name}_SOURCES main.cpp)

add_executable(${project_name} ${${project_name}_SOURCES})
target_link_libraries(${project_name} ${${project_name}_external_libs})

install(TARGETS ${project_name} RUNTIME DESTINATION ${CMAKE_BINARY_DIR})