cmake_minimum_required(VERSION 3.18)
project(tag_invoke_wrapper_lib NONE)

include (FetchContent)

FetchContent_Declare(tag_invoke
  GIT_REPOSITORY     https://gist.github.com/ericniebler/056f5459cf259da526d9ea2279c386bb
  GIT_TAG            master)
FetchContent_MakeAvailable(tag_invoke)
FetchContent_GetProperties(tag_invoke)

add_library(tag_invoke_wrapper_lib INTERFACE)
target_include_directories(tag_invoke_wrapper_lib INTERFACE
  $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>
  $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/${tag_invoke_SOURCE_DIR}>)
target_compile_features(tag_invoke_wrapper_lib INTERFACE cxx_std_20)
add_library(tag_invoke_wrapper::tag_invoke ALIAS tag_invoke_wrapper_lib)
