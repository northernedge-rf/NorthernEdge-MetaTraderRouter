cmake_minimum_required(VERSION 3.15)
project(NorthernEdge_MetaTraderRouter VERSION 2.4 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Optimization flags for high-frequency trading & robotics
if(MSVC)
    add_compile_options(/O2 /W4 /WX)
else()
    add_compile_options(-O3 -Wall -Wextra -Wpedantic -Werror -pthread)
endif()

add_executable(mt_router src/main.cpp)

enable_testing()
