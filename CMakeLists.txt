include(FetchContent)
cmake_minimum_required(VERSION 3.17)

project(voxeloop-base)

set(CMAKE_CXX_STANDARD 17)

# Turn OFF GLFW options
set(GLFW_BUILD_EXAMPLES OFF)
set(GLFW_BUILD_TESTS OFF)
set(GLFW_BUILD_DOCS OFF)

FetchContent_Declare(
        glfw
        GIT_REPOSITORY https://github.com/glfw/glfw.git
        GIT_TAG 3.3.6
)
FetchContent_Declare(
        glm
        GIT_REPOSITORY https://github.com/g-truc/glm.git
        GIT_TAG 0.9.9.8
)

FetchContent_MakeAvailable(glfw glm)
add_subdirectory(glad)
add_subdirectory(imgui)
add_subdirectory(stb)
