add_library(api_clib "")

target_sources(api_clib
        PRIVATE
        CAssertClass.cpp
        CTypeClass.cpp
        CErrnoClass.cpp
        CLimitsClass.cpp
        CLocaleClass.cpp
        CSignalClass.cpp
        CStdioClass.cpp
        CStdlibClass.cpp
        CStringClass.cpp
        CTimeClass.cpp
        CArpaInetClass.cpp
        CConioClass.cpp
        CDirentClass.cpp
        CFcntlClass.cpp
        CNetdbClass.cpp
        CNetinetInClass.cpp
        CSpawnClass.cpp
        CSysSelectClass.cpp
        CSysSocketClass.cpp
        CSysStatClass.cpp
        CSysUtsnameClass.cpp
        CSysWaitClass.cpp
        CUnistdClass.cpp

        PUBLIC
        CAssertClass.h
        CTypeClass.h
        CErrnoClass.h
        CLimitsClass.h
        CLocaleClass.h
        CSignalClass.h
        CStdioClass.h
        CStdlibClass.h
        CStringClass.h
        CTimeClass.h
        CArpaInetClass.h
        CConioClass.h
        CDirentClass.h
        CFcntlClass.h
        CNetdbClass.h
        CNetinetInClass.h
        CSpawnClass.h
        CSysSelectClass.h
        CSysSocketClass.h
        CSysStatClass.h
        CSysUtsnameClass.h
        CSysWaitClass.h
        CUnistdClass.h)

target_link_libraries(api_clib core)
target_include_directories(api_clib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})