cmake_minimum_required(VERSION 3.18)
project(tdlib_jni)

# Find TDLib
include_directories(${CMAKE_SOURCE_DIR}/include)

# Set the library name
add_library(tdlib_jni SHARED
        TdLibJNI.c  # Your JNI bridge file
)

# Link TDLib
target_link_libraries(tdlib_jni
        ${CMAKE_SOURCE_DIR}/libs/macOS/libtdjson.dylib
)

find_library(log-lib log)
target_link_libraries(tdlib_jni ${log-lib})