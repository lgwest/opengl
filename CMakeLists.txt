cmake_minimum_required(VERSION 3.10)

set(OpenGL_GL_PREFERENCE GLVND)

include(FetchContent)
FetchContent_Declare(
        glew
        GIT_REPOSITORY https://github.com/nigels-com/glew
        GIT_TAG        glew-2.1.0
)
FetchContent_Declare(
        glfw
        GIT_REPOSITORY https://github.com/glfw/glfw
        GIT_TAG        3.2.1
)
FetchContent_Declare(
        glm
        GIT_REPOSITORY https://github.com/g-truc/glm
        GIT_TAG        0.9.9.3
)
FetchContent_Declare(
        assimp
        GIT_REPOSITORY https://github.com/assimp/assimp
        GIT_TAG        v4.1.0
)

message("-- Building GLEW ...")
FetchContent_Populate(glew)
add_subdirectory(${glew_SOURCE_DIR}/build/cmake ${glew_BINARY_DIR})
message("-- Building GLFW ...")
FetchContent_Populate(glfw)
add_subdirectory(${glfw_SOURCE_DIR} ${glfw_BINARY_DIR})
message("-- Building GLM ...")
FetchContent_Populate(glm)
add_subdirectory(${glm_SOURCE_DIR} ${glm_BINARY_DIR})
message("-- Building ASSIMP ...")
FetchContent_Populate(assimp)
add_subdirectory(${assimp_SOURCE_DIR} ${assimp_BINARY_DIR})
message("-----------------------------------------")
# find GLEW
#find_package(GLEW REQUIRED)
#message("GLEW_INCLUDE_DIRS is ${GLEW_INCLUDE_DIRS}")
#message("GLEW_LIBRARIES is ${GLEW_LIBRARIES}")

# find GLFW
#find_package(PkgConfig REQUIRED)
#pkg_search_module(GLFW REQUIRED glfw3)
#message("GLFW_INCLUDE_DIRS is ${GLFW_INCLUDE_DIRS}")
#message("GLFW_LIBRARIES is ${GLFW_LIBRARIES}")
#message("GLFW_STATIC_LIBRARIES is ${GLFW_STATIC_LIBRARIES}")

# find OpenGL
find_package(OpenGL REQUIRED)
message("OPENGL_FOUND is ${OPENGL_FOUND}")
message("OPENGL_XMESA_FOUND is ${OPENGL_XMESA_FOUND}")
message("OPENGL_GLU_FOUND is ${OPENGL_GLU_FOUND}")
message("OPENGL_INCLUDE_DIR is ${OPENGL_INCLUDE_DIR}")
message("OPENGL_LIBRARIES is ${OPENGL_LIBRARIES}")
message("OPENGL_gl_LIBRARY is ${OPENGL_gl_LIBRARY}")
message("OPENGL_glu_LIBRARY is ${OPENGL_glu_LIBRARY}")

# find glm
#find_package(glm REQUIRED)
#message("glm_INCLUDE_DIRS")

#find_package(assimp REQUIRED)
#message("assimp_INCLUDE_DIRS is ${assimp_INCLUDE_DIRS}")
#message("assimp_LIBRARIES is ${assimp_LIBRARIES}")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CONFIG_DIR ${CMAKE_CURRENT_SOURCE_DIR}/config)

set(OPENGL_INCLUDE_DIRS ${OPENGL_INCLUDE_DIR})
set(OPENGL_LIBRARIES ${OPENGL_LIBRARIES})
set(GLEW_INCLUDE_DIRS ${OPENGL_INCLUDE_DIR})
set(GLEW_LIBRARIES ${OPENGL_LIBRARIES})
set(GLFW_INCLUDE_DIRS ${OPENGL_INCLUDE_DIR})
set(GLFW_LIBRARIES ${OPENGL_LIBRARIES})

message("CMAKE_BUILD_TYPE is ${CMAKE_BUILD_TYPE}")
message("xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx")
add_subdirectory(1-introduction)
#add_subdirectory(2-beginner)
#add_subdirectory(3-camera)
#add_subdirectory(4-intermediate)
#add_subdirectory(5-advanced)
message("yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy")