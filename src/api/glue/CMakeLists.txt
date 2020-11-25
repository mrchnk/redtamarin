add_library(api_glue
    SystemClass.cpp
    FileGlueClass.cpp
    FileReferenceClass.cpp
    SystemClass.h)

target_link_libraries(api_glue core)
target_include_directories(api_glue PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})