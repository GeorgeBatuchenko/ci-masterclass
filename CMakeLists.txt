cmake_minimum_required(VERSION 3.0)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

target_link_libraries(${PROJECT_NAME} ${CONAN_LIBS})

project(ci-masterclass CXX)

include_directories(include)

set(${PROJECT_NAME}_SRC
	src/main.cpp
)

add_library(${PROJECT_NAME} ${${PROJECT_NAME}_SRC})

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 14)

enable_testing()
add_subdirectory(test)
