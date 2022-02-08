include(FetchContent)
cmake_minimum_required(VERSION 3.17)

project(voxeloop)

set(CMAKE_CXX_STANDARD 17)

set(BUILD_SHARED_LIBS OFF)
FetchContent_Declare(
        voxeloop-base
        GIT_REPOSITORY https://github.com/cmmw/imgui-glfw-glad-glm.git
        GIT_TAG v3.3.5
)
FetchContent_MakeAvailable(voxeloop-base)

add_executable(voxeloop main.cpp)

target_link_libraries(
        voxeloop
        imgui
        glm
)