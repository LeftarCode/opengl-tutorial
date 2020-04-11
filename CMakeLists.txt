cmake_minimum_required(VERSION 3.10)

project(opengl)

IF(NOT MSVC)
  MESSAGE(FATAL_ERROR "Compilers other than Visual Studio is not yet supported")
ENDIF()

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
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glew-2.1.0/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glfw-3.3.2/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glm-0.9.9.7)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/stb)

link_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/assimp-5.0.1/lib)
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glew-2.1.0/lib/Release/x64)
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glfw-3.3.2/lib-${GLFW_LIB_DIR})

add_subdirectory(opengl0)