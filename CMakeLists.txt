cmake_minimum_required(VERSION 3.10)

# find GLEW
find_package(GLEW REQUIRED)
message("GLEW_INCLUDE_DIRS is ${GLEW_INCLUDE_DIRS}")
message("GLEW_LIBRARIES is ${GLEW_LIBRARIES}")

# find GLFW
find_package(PkgConfig REQUIRED)
pkg_search_module(GLFW REQUIRED glfw3)
message("GLFW_INCLUDE_DIRS is ${GLFW_INCLUDE_DIRS}")
message("GLFW_LIBRARIES is ${GLFW_LIBRARIES}")
message("GLFW_STATIC_LIBRARIES is ${GLFW_STATIC_LIBRARIES}")

# find OpenGL
set(OpenGL_GL_PREFERENCE GLVND)
find_package(OpenGL REQUIRED)
message("OPENGL_INCLUDE_DIRS is ${OPENGL_INCLUDE_DIRS}")
message("OPENGL_LIBRARIES is ${OPENGL_LIBRARIES}")

# find glm
find_package(glm REQUIRED)
message("glm_INCLUDE_DIRS")

find_package(assimp REQUIRED)
message("assimp_INCLUDE_DIRS is ${assimp_INCLUDE_DIRS}")
message("assimp_LIBRARIES is ${assimp_LIBRARIES}")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CONFIG_DIR ${CMAKE_CURRENT_SOURCE_DIR}/config)

add_subdirectory(1-introduction)
add_subdirectory(2-beginner)
add_subdirectory(3-camera)
add_subdirectory(4-intermediate)
