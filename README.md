# voxeloop-base

A CMake project for [GLFW](https://github.com/glfw/glfw)
, [Glad](https://gen.glad.sh/), [ImGui](https://github.com/ocornut/imgui) and
[glm](https://github.com/g-truc/glm).

This project is meant to simplify the import of the OpenGL related libraries
GLFW, ImGui, Glad and glm. GLFW and glm are included via CMake's FetchContent
.
Glad is added manually via source code.

Fork of: [https://github.com/RujalAcharya/voxeloop-base.git](https://github.com/cmmw/imgui-glfw-glad-glm)


### Example

In order to use the libraries, simply include this project with CMake's
FetchContent:

```cmake
include(FetchContent)

# ...

# Use static libraries
set(BUILD_SHARED_LIBS OFF)
FetchContent_Declare(
        voxeloop-base
        GIT_REPOSITORY https://github.com/RujalAcharya/voxeloop-base.git
        GIT_TAG main
)

FetchContent_MakeAvailable(voxeloop-base)

add_executable(
        app
        main.cpp
)

# It is sufficient to only link glm and ImGui since the latter one already contains Glad and GLFW
target_link_libraries(
        app
        imgui
        glm
)

# Otherwise link only Glad, GLFW and glm if ImGui is not needed
target_link_libraries(
        app
        glfw
        glad
        glm
)

```

The folder example provides a minimal, self-contained sample program which
includes this project via FetchContent and does all the necessary initialization
of the components. In order to build it, create a build folder inside the
example directory, cd into it and execute

```shell
cmake .. -G "<Generator of your choice>"
cmake --build . --target app
```

If preferred, libraries can be built separately and included in your projects.

### License

The content of this project (excluding 3rd party libraries) is licensed under
the [MIT license](https://github.com/cmmw/imgui-glfw-glad/blob/master/LICENSE.md)
. Please refer to the particular libraries homepage/repository for more
information regarding licensing.