project(opengl0)

add_executable(opengl0 main.cpp)

target_link_libraries(opengl0 assimp)
target_link_libraries(opengl0 glew_s)
target_link_libraries(opengl0 glfw)
