include(FetchContent)
cmake_minimum_required(VERSION 3.17)

project(example)

set(CMAKE_CXX_STANDARD 17)

set(BUILD_SHARED_LIBS OFF)
FetchContent_Declare(
        voxeloop-base
        GIT_REPOSITORY https://github.com/RujalAcharya/voxeloop-base.git
        GIT_TAG main 
)
FetchContent_MakeAvailable(voxeloop-base)

add_executable(app main.cpp)

target_link_libraries(
        app
        imgui
        glm
)
