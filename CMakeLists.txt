cmake_minimum_required(VERSION 3.20)
project(IndexIt LANGUAGES C)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS OFF)

include_directories(${CMAKE_SOURCE_DIR}/include)

file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS
    ${CMAKE_SOURCE_DIR}/src/*.c
)

add_executable(indexit ${SOURCES})

target_include_directories(indexit PRIVATE ${CMAKE_SOURCE_DIR}/include)

# Optional: enable warnings for compiler quality
if (MSVC)
    target_compile_options(indexit PRIVATE /W4)
else()
    target_compile_options(indexit PRIVATE -Wall -Wextra -Wpedantic)
endif()
