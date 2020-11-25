add_library(shell
avmshell.cpp
ConsoleOutputStream.cpp
DebugCLI.cpp
DomainClass.cpp
FileInputStream.cpp
ShellCore.cpp
ProgramClass.cpp
swf.cpp
ShellWorkerGlue.cpp
ShellWorkerDomainGlue.cpp

avmshellMac.cpp
PosixFile.cpp
PosixPartialPlatform.cpp

avmshell-features.h
)

target_link_libraries(shell core vmbase eval extensions api_clib api_shell api_glue)
target_include_directories(shell PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})