add_library(platform
        unix/MathUtilsUnix.cpp
        unix/OSDepUnix.cpp
        system-selection.h)

target_link_libraries(platform core)
target_include_directories(platform PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
