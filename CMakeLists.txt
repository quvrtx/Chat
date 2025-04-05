cmake_minimum_required(VERSION 3.10)
project(Chat)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(SFML 3.0 COMPONENTS system window graphics network audio REQUIRED)

include_directories(include)

file(GLOB SERVER_SOURCES "server/*.cpp")
file(GLOB CLIENT_SOURCES "client/*.cpp")

add_executable(server ${SERVER_SOURCES})
add_executable(client ${CLIENT_SOURCES})

target_link_libraries(server PRIVATE 
    SFML::Network 
    SFML::System
)

target_link_libraries(client PRIVATE 
    SFML::Network 
    SFML::System
)
