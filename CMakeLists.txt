cmake_minimum_required(VERSION 3.10)

project(opengl)

IF(NOT MSVC)
  MESSAGE(FATAL_ERROR "Compilers other than Visual Studio is not yet supported")
ENDIF()

# GLFW OPTIONS
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(BUILD_SHARED_LIBS OFF CACHE BOOL "" FORCE)

# GLEW OPTIONS
set(GLEW_USE_STATIC_LIBS ON CACHE BOOL "" FORCE)

add_definitions(
    -DTW_STATIC
    -DTW_NO_LIB_PRAGMA
    -DTW_NO_DIRECT3D
    -DGLEW_STATIC
)

if(MSVC)
  if( MSVC11 )
    set(GLFW_LIB_DIR "vc2012")
  elseif( MSVC12 )
    set(GLFW_LIB_DIR "vc2013")
  elseif( MSVC_VERSION LESS 1910)
    set(GLFW_LIB_DIR "vc2015")
  elseif( MSVC_VERSION LESS 1920)
    set(GLFW_LIB_DIR "vc2017")
  elseif( MSVC_VERSION LESS 1930)
    set(GLFW_LIB_DIR "vc2019")
  endif()
endif()

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/assimp-5.0.1/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glew-cmake/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glfw/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glm)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/stb)

link_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/assimp-5.0.1/lib)
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glew-cmake/lib)
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glfw/lib/)

# DEPENDENCIES
add_subdirectory(libs/glew-cmake/build/cmake)
add_subdirectory(libs/glfw)

# PROJECTS
add_subdirectory(opengl0)