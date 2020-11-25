add_library(VMPI "")

target_sources(VMPI
        PRIVATE
        GenericPortUtils.cpp

        PUBLIC
        VMPI.h)

if (${CMAKE_HOST_WIN32})
    target_sources(VMPI
            PRIVATE
            WinDebugUtils.cpp
            WinPortUtils.cpp
            WinPortUtils2.cpp
            ThreadsWin.cpp)
elseif (${CMAKE_HOST_APPLE})
    target_sources(VMPI
            PRIVATE
            MacDebugUtils.cpp
            MacPortUtils.cpp
            PosixPortUtils.cpp
            PosixPortUtils2.cpp
            ThreadsPosix.cpp)
elseif (${CMAKE_HOST_UNIX})
    target_sources(VMPI
            PRIVATE
            PosixPortUtils.cpp
            PosixPortUtils2.cpp
            PosixSpecificUtils.cpp
            UnixDebugUtils.cpp
            ThreadsPosix.cpp)
endif()

target_link_libraries(VMPI platform)
target_include_directories(VMPI PUBLIC ${CMAKE_CURRENT_LIST_DIR})