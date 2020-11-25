add_library(AVMPI
  AvmAssert.cpp
  float4Support.cpp
  PosixMMgcPortUtils.cpp
  MMgcPortMac.cpp
  SpyUtilsPosix.cpp
  AVMPI.h
)

target_link_libraries(AVMPI VMPI shell)
target_include_directories(AVMPI PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
