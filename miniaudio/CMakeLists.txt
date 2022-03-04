add_library(
    miniaudio
    miniaudio.h
)

target_link_libraries(miniaudio)

target_include_directories(
    miniaudio
    PUBLIC
    miniaudio
)
