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

# finf OpenGL
find_package(OpenGL REQUIRED)
message("OPENGL_INCLUDE_DIRS is ${OPENGL_INCLUDE_DIRS}")
message("OPENGL_LIBRARIES is ${OPENGL_LIBRARIES}")

add_subdirectory(1-beginner)
