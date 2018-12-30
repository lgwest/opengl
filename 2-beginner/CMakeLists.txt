project(2-beginner)

include_directories(
${OPENGL_INCLUDE_DIRS} 
${GLEW_INCLUDE_DIRS} 
${GLWF_INCLUDE_DIRS}
${GLM_INCLUDE_DIRS}
)

add_executable(2-triangle triangle.cpp)
target_link_libraries(2-triangle
${OPENGL_LIBRARIES} 
${GLEW_LIBRARIES} 
${GLFW_LIBRARIES}
)

add_executable(2-uniform uniform.cpp)
target_link_libraries(2-uniform
${OPENGL_LIBRARIES}
${GLEW_LIBRARIES}
${GLFW_LIBRARIES}
)

add_executable(2-translate translate.cpp)
target_link_libraries(2-translate
${OPENGL_LIBRARIES}
${GLEW_LIBRARIES}
${GLFW_LIBRARIES}
)
