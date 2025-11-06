# ===============================================
# OpenGL项目 CMake模板
# ===============================================

cmake_minimum_required(VERSION 3.15)

# 项目名称（修改这里）
project(firstTriangle LANGUAGES CXX C)

# C++标准
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# ========================================
# 修复CMake 4.2.0与MinGW兼容性问�?
# ========================================
# 禁用响应文件（response files�?
set(CMAKE_C_USE_RESPONSE_FILE_FOR_INCLUDES OFF)
set(CMAKE_CXX_USE_RESPONSE_FILE_FOR_INCLUDES OFF)
set(CMAKE_C_USE_RESPONSE_FILE_FOR_OBJECTS OFF)
set(CMAKE_CXX_USE_RESPONSE_FILE_FOR_OBJECTS OFF)
set(CMAKE_C_USE_RESPONSE_FILE_FOR_LIBRARIES OFF)
set(CMAKE_CXX_USE_RESPONSE_FILE_FOR_LIBRARIES OFF)

# 编译器警�?
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wextra")

# 设置库路径（根据实际情况修改�?
set(LIBS_PATH "D:/desktop/Code/Libraries")

# 源文件
set(SOURCES
    src/triangle.cpp
    ${LIBS_PATH}/GLAD/src/glad.c
)

# 生成可执行文�?
add_executable(${PROJECT_NAME} ${SOURCES})

# 包含头文件目�?
target_include_directories(${PROJECT_NAME} PRIVATE
    ${LIBS_PATH}/GLAD/include
    ${LIBS_PATH}/GLFW/include
    ${CMAKE_SOURCE_DIR}/include
)

# 链接库目�?
target_link_directories(${PROJECT_NAME} PRIVATE
    ${LIBS_PATH}/GLFW/lib-mingw-w64
)

# 链接�?
target_link_libraries(${PROJECT_NAME} PRIVATE
    glfw3
    opengl32
    gdi32
)

# 输出信息
message(STATUS "项目名称: ${PROJECT_NAME}")
message(STATUS "库路�? ${LIBS_PATH}")
message(STATUS "GLFW: ${LIBS_PATH}/GLFW")
message(STATUS "GLAD: ${LIBS_PATH}/GLAD")

