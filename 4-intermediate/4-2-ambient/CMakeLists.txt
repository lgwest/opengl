project(4-2-ambient)

configure_file(${CONFIG_DIR}/current_dir.h.in ${CMAKE_CURRENT_SOURCE_DIR}/current_dir.h)

add_executable(${PROJECT_NAME}
        Camera.cpp
        Camera.h
        current_dir.h
        Light.cpp
        Light.h
        main.cpp
        Mesh.cpp
        Mesh.h
        Shader.cpp
        Shader.h
        stb_image.h
        Texture.cpp
        Texture.h
        Window.cpp
        Window.h
        )

target_link_libraries(${PROJECT_NAME}
        ${OPENGL_LIBRARIES}
        ${GLEW_LIBRARIES}
        ${GLFW_LIBRARIES}
        )

