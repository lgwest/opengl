project(2-beginner)

include_directories(
${OPENGL_INCLUDE_DIRS} 
${GLEW_INCLUDE_DIRS} 
${GLWF_INCLUDE_DIRS}
${GLM_INCLUDE_DIRS}
)

add_executable(2-1-triangle 2-1-triangle.cpp)
target_link_libraries(2-1-triangle
${OPENGL_LIBRARIES} 
${GLEW_LIBRARIES} 
${GLFW_LIBRARIES}
)

add_executable(2-2-uniform 2-2-uniform.cpp)
target_link_libraries(2-2-uniform
${OPENGL_LIBRARIES}
${GLEW_LIBRARIES}
${GLFW_LIBRARIES}
)

add_executable(2-3-translate 2-3-translate.cpp)
target_link_libraries(2-3-translate
${OPENGL_LIBRARIES}
${GLEW_LIBRARIES}
${GLFW_LIBRARIES}
)
