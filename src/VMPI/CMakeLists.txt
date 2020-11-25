add_library(VMPI
    MacDebugUtils.cpp
    MacPortUtils.cpp
    PosixPortUtils.cpp
    PosixPortUtils2.cpp
    GenericPortUtils.cpp
    ThreadsPosix.cpp
    VMPI.h)

target_link_libraries(VMPI platform)
target_include_directories(VMPI PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})