cmake_minimum_required(VERSION 3.14)

set(GLEW_TAG c14a7a1) # git hash: May 1, 2019
set(GLFW_TAG 3.3)
set(GLM_TAG 0.9.9.5)

include(FetchContent)

# Fetch and build GLEW
add_definitions(-DGLEW_STATIC)
FetchContent_Declare(
	glewlib
	GIT_REPOSITORY https://github.com/Perlmint/glew-cmake.git
	GIT_TAG ${GLEW_TAG}
)
FetchContent_MakeAvailable(glewlib)
set(GLEW_INCLUDE_DIRS ${glew_SOURCE_DIR}/include)
set(GLEW_LIBRARIES libglew_static libglewmx_static)

message("GLEW_INCLUDE_DIRS is ${GLEW_INCLUDE_DIRS}")
message("GLEW_LIBRARIES is ${GLEW_LIBRARIES}")

# Fetch and build GLFW
# see: https://www.glfw.org/docs/latest/build.html#build_link_cmake_source
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
FetchContent_Declare(
	glfwlib
	GIT_REPOSITORY https://github.com/glfw/glfw.git
	GIT_TAG ${GLFW_TAG}
)
FetchContent_MakeAvailable(glfwlib)

set(GLFW_INCLUDE_DIRS ${glfwlib_SOURCE_DIR}/include)
set(GLFW_LIBRARIES glfw)

# Fetch GLM
FetchContent_Declare(
	glmlib
	GIT_REPOSITORY https://github.com/g-truc/glm.git
	GIT_TAG ${GLM_TAG}
)
FetchContent_MakeAvailable(glmlib)
set(GLM_INCLUDE_DIRS ${glmlib_SOURCE_DIR})


# find OpenGL
set(OpenGL_GL_PREFERENCE GLVND)
find_package(OpenGL REQUIRED)
message("OPENGL_INCLUDE_DIR is ${OPENGL_INCLUDE_DIR}")
message("OPENGL_LIBRARIES is ${OPENGL_LIBRARIES}")

# find glm
#find_package(glm REQUIRED)
#message("glm_INCLUDE_DIRS")

#find_package(assimp REQUIRED)
#message("assimp_INCLUDE_DIRS is ${assimp_INCLUDE_DIRS}")
#message("assimp_LIBRARIES is ${assimp_LIBRARIES}")
include_directories(${GLM_INCLUDE_DIRS})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CONFIG_DIR ${CMAKE_CURRENT_SOURCE_DIR}/config)
link_directories(${CMAKE_BINARY_DIR}/lib)

add_subdirectory(1-introduction)
add_subdirectory(2-beginner)
add_subdirectory(3-camera)
#add_subdirectory(4-intermediate)
#add_subdirectory(5-advanced)
