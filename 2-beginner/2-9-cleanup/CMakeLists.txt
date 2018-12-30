project(2-9-cleanup)

include_directories(${CMAKE_CURRENT_SRC_DIR})

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

