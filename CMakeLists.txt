cmake_minimum_required(VERSION 3.15)
project(HackerArena)

set(CMAKE_CXX_STANDARD 17)

# Boost is header-only for Asio
find_package(Boost REQUIRED)

# Client executable
add_executable(client
  client/main.cpp
)
target_include_directories(client PRIVATE ${Boost_INCLUDE_DIRS})

# Server executable
add_executable(server
  server/main.cpp
)
target_include_directories(server PRIVATE ${Boost_INCLUDE_DIRS})
