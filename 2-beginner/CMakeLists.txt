project(2-beginner)

include_directories(
${OPENGL_INCLUDE_DIRS} 
${GLEW_INCLUDE_DIRS} 
${GLWF_INCLUDE_DIRS}
${GLM_INCLUDE_DIRS}
)

macro(add_myexe binName)
    add_executable(${binName} ${binName}.cpp)
    target_link_libraries(${binName}
            ${OPENGL_LIBRARIES}
            ${GLEW_LIBRARIES}
            ${GLFW_LIBRARIES}
            )

endmacro()

add_myexe(2-1-triangle)
add_myexe(2-2-uniform)
add_myexe(2-3-translate)
add_myexe(2-4-rotate)
add_myexe(2-5-scale)
add_myexe(2-6-interpolation)
add_myexe(2-7-indexing)
add_myexe(2-8-projections)
add_subdirectory(2-9-cleanup)
