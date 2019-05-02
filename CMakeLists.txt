cmake_minimum_required(VERSION 3.0.2)

project(luafilesystem)

find_package(Lua REQUIRED)

SET(CMAKE_CXX_FLAGS "-Wall -fPIC -W -Waggregate-return -Wcast-align -Wmissing-prototypes -Wnested-externs -Wshadow -Wwrite-strings -pedantic")
SET(CMAKE_CXX_FLAGS_DEBUG  "-O0 -g")
SET(CMAKE_CXX_FLAGS_RELEASE "-O2")

# 
SET(TARGET_NAME "lfs")
add_library(${TARGET_NAME} SHARED "src/lfs.c")
target_link_libraries(${TARGET_NAME} ${LUA_LIBRARIES})