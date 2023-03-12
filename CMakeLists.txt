cmake_minimum_required(VERSION 3.3)
project(MusicBot LANGUAGES CXX C)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS_RELEASE -O3)
set(CMAKE_CXX_FLAGS_DEBUG "-Wall -Wextra")

set(SOURCES
  "src/Main.cpp"
)

add_executable(MusicBot ${SOURCES})

# spdlog
option(SPDLOG_ENABLE_PCH ON)

add_subdirectory("lib/spdlog")
target_link_libraries(${PROJECT_NAME} PRIVATE spdlog)