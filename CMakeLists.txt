cmake_minimum_required(VERSION 3.12)

project(cmake-lib-demo)

add_executable(${PROJECT_NAME} demo.c)
target_link_directories(${PROJECT_NAME} PRIVATE libsample)
target_link_libraries(${PROJECT_NAME} PRIVATE sample)
