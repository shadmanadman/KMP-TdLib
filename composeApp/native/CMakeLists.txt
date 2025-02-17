cmake_minimum_required(VERSION 3.18)
project(tdlib_jni)

add_library(tdlib_jni SHARED TdLibJNI.c)

find_library(log-lib log)

target_link_libraries(tdlib_jni ${CMAKE_SOURCE_DIR}/lib/macOS/tdjson)