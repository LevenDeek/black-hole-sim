cmake_minimum_required(VERSION 3.20)
project(black_hole)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(GLEW REQUIRED)
find_package(glfw3 CONFIG REQUIRED)
find_package(glm CONFIG REQUIRED)
find_package(OpenGL REQUIRED)

# Main 3D Black Hole Simulation
add_executable(black_hole black_hole-main/black_hole.cpp)
target_link_libraries(black_hole PRIVATE GLEW::GLEW glfw glm::glm OpenGL::GL)

# 2D Lensing Simulation
add_executable(2D_lensing black_hole-main/2D_lensing.cpp)
target_link_libraries(2D_lensing PRIVATE GLEW::GLEW glfw glm::glm OpenGL::GL)

# CPU Geodesic
add_executable(CPU_geodesic black_hole-main/CPU-geodesic.cpp)
target_link_libraries(CPU_geodesic PRIVATE GLEW::GLEW glfw glm::glm OpenGL::GL)

# Ray Tracing
add_executable(ray_tracing black_hole-main/ray_tracing.cpp)
target_link_libraries(ray_tracing PRIVATE GLEW::GLEW glfw glm::glm OpenGL::GL)