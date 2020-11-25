cmake_minimum_required(VERSION 3.14)
project(redtamarin)

set(CMAKE_CXX_STANDARD 14)
#set(CMAKE_VERBOSE_MAKEFILE ON)

add_definitions(-DAVMSHELL_BUILD)
add_executable(avm "")

if (${CMAKE_HOST_WIN32})
    add_definitions(-DWIN32)
    add_definitions(-D_M_X64)
    target_sources(avm
            PRIVATE
            src/shell/avmshellWin.cpp)
    target_link_libraries(avm shell)
elseif (${CMAKE_HOST_APPLE})
    add_definitions(-D_MAC)
    target_sources(avm
            PRIVATE
            src/shell/avmshellMac.cpp)
    target_link_libraries(avm shell)
elseif (${CMAKE_HOST_UNIX})
    add_definitions(-DUNIX)
    target_sources(avm
            PRIVATE
            src/shell/avmshellUnix.cpp)
    set(THREADS_PREFER_PTHREAD_FLAG ON)
    find_package(Threads REQUIRED)
    target_link_libraries(avm PRIVATE shell Threads::Threads)
endif ()

add_subdirectory(src/core)
add_subdirectory(src/platform)
add_subdirectory(src/VMPI)
add_subdirectory(src/AVMPI)
add_subdirectory(src/vmbase)
add_subdirectory(src/shell)
add_subdirectory(src/generated)
add_subdirectory(src/MMgc)
add_subdirectory(src/eval)
add_subdirectory(src/extensions)
add_subdirectory(src/api)
add_subdirectory(src/pcre)
add_subdirectory(src/other-licenses/lzma)
add_subdirectory(src/other-licenses/zlib)
add_subdirectory(src/nanojit)
