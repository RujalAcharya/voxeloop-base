add_library(
    miniaudio
    miniaudio/miniaudio.h
    miniaudio/miniaudio.c
)

target_link_libraries(miniaudio)

target_include_directories(
    miniaudio
    PUBLIC
    miniaudio
)
