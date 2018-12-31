project(2-9-cleanup)

configure_file(${CONFIG_DIR}/current_dir.h.in ${CMAKE_CURRENT_SOURCE_DIR}/current_dir.h)

add_executable(${PROJECT_NAME}
main.cpp 
Mesh.cpp 
Mesh.h 
Shader.cpp 
Shader.h
Window.cpp
Window.h
)

target_link_libraries(${PROJECT_NAME}
${OPENGL_LIBRARIES}
${GLEW_LIBRARIES}
${GLFW_LIBRARIES}
)

