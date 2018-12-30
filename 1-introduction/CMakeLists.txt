project(1-beginner)

include_directories(
${OPENGL_INCLUDE_DIRS} 
${GLEW_INCLUDE_DIRS} 
${GLWF_INCLUDE_DIRS}
)

add_executable(${PROJECT_NAME} main.cpp)
target_link_libraries(${PROJECT_NAME} 
${OPENGL_LIBRARIES} 
${GLEW_LIBRARIES} 
${GLFW_LIBRARIES}
)


