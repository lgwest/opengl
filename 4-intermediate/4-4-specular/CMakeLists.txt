project(4-4-specular)

configure_file(${CONFIG_DIR}/current_dir.h.in ${CMAKE_CURRENT_SOURCE_DIR}/current_dir.h)

add_executable(${PROJECT_NAME}
        Camera.cpp
        Camera.h
        CMakeLists.txt
        current_dir.h
        Light.cpp
        Light.h
        main.cpp
        Material.cpp
        Material.h
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

