add_library(api_shell
    RuntimeClass.cpp
    DiagnosticsClass.cpp
    HardwareInformationClass.cpp
    OperatingSystemClass.cpp
    FileSystemClass.cpp
    RuntimeClass.h)

target_link_libraries(api_shell core)
target_include_directories(api_shell PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})