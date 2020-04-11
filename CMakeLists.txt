cmake_minimum_required(VERSION 3.10)
project(opengltutorial)

IF(NOT MSVC)
  MESSAGE(FATAL_ERROR "Compilers other than Visual Studio is not yet supported")
ENDIF()

# CMAKE OPTIONS
set(CMAKE_SUPPRESS_REGENERATION true)
set(BUILD_SHARED_LIBS OFF CACHE BOOL "" FORCE)
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

# GLFW OPTIONS
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

# GLEW OPTIONS
set(GLEW_USE_STATIC_LIBS ON CACHE BOOL "" FORCE)

add_definitions(
    -DTW_STATIC
    -DTW_NO_LIB_PRAGMA
    -DTW_NO_DIRECT3D
    -DGLEW_STATIC
)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/assimp/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glew-cmake/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glfw/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glm)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/stb)

link_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/assimp/lib)
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glew-cmake/lib)
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glfw/lib/)

# DEPENDENCIES
add_subdirectory(libs/assimp)
add_subdirectory(libs/glew-cmake/build/cmake)
add_subdirectory(libs/glfw)

# PROJECTS - EPISODES
add_subdirectory(episode0)



# PROJECT STRUCTURE
set_target_properties(assimp PROPERTIES FOLDER "Assimp")
set_target_properties(assimp_cmd PROPERTIES FOLDER "Assimp")
set_target_properties(UpdateAssimpLibsDebugSymbolsAndDLLs PROPERTIES FOLDER "Assimp")
set_target_properties(uninstall PROPERTIES FOLDER "Assimp")
set_target_properties(IrrXML PROPERTIES FOLDER "Assimp")
set_target_properties(unit PROPERTIES FOLDER "Assimp")
set_target_properties(zlib PROPERTIES FOLDER "Assimp")
set_target_properties(zlibstatic PROPERTIES FOLDER "Assimp")

set_target_properties(glew PROPERTIES FOLDER "GLEW")
set_target_properties(glew_s PROPERTIES FOLDER "GLEW")
set_target_properties(glewinfo PROPERTIES FOLDER "GLEW")
set_target_properties(visualinfo PROPERTIES FOLDER "GLEW")

set_target_properties(episode0 PROPERTIES FOLDER "Episodes")