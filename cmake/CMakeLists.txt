cmake_minimum_required(VERSION 3.16)
project(sfml-template)

set(CMAKE_CSS_STANDARD 17)
set(SRC_DIR ../src)
set(BIN_DIR ../bin)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/${BIN_DIR})

find_package(SFML 2.5 COMPONENTS system window graphics REQUIRED)

file(GLOB ENGINE_SOURCES ${SRC_DIR}/engine/*.cpp ${SRC_DIR}/engine/*.h)
file(GLOB AI_SOURCES ${SRC_DIR}/ai/*.cpp ${SRC_DIR}/ai/*.h)

add_executable(sfml-template ${ENGINE_SOURCES} ${AI_SOURCES} ${SRC_DIR}/main.cpp)

target_link_libraries(sfml-template PRIVATE sfml-system sfml-window sfml-graphics)
