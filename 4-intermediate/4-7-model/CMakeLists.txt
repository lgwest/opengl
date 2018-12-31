project(4-)

configure_file(${CONFIG_DIR}/current_dir.h.in ${CMAKE_CURRENT_SOURCE_DIR}/current_dir.h)

add_executable(${PROJECT_NAME}
        Camera.cpp
        Camera.h
        CMakeLists.txt
        CommonValues.h
        current_dir.h
        DirectionalLight.cpp
        DirectionalLight.h
        Light.cpp
        Light.h
        main.cpp
        Material.cpp
        Material.h
        Mesh.cpp
        Mesh.h
        Model.cpp
        Model.h
        Models
        PointLight.cpp
        PointLight.h
        Shader.cpp
        Shader.h
        Shaders
        SpotLight.cpp
        SpotLight.h
        stb_image.h
        Texture.cpp
        Texture.h
        Textures
        Window.cpp
        Window.h
        )

target_link_libraries(${PROJECT_NAME}
        ${OPENGL_LIBRARIES}
        ${GLEW_LIBRARIES}
        ${GLFW_LIBRARIES}
        )

