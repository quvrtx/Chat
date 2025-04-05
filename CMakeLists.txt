cmake_minimum_required(VERSION 3.10)
project(Chat)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_compile_options(-Wall -Wextra -pedantic -lsfml-network -lsfml-system)

include_directories(include)

file(GLOB SERVER_SOURCES "server/*.cpp")
file(GLOB CLIENT_SOURCES "client/*.cpp")

add_executable(server ${SERVER_SOURCES})
add_executable(client ${CLIENT_SOURCES})