cmake_minimum_required(VERSION 3.10)
project(oatpp_demo)

# 设置 C++ 标准
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# 包含 oatpp 的头文件路径
include_directories("/usr/local/include/oatpp-1.3.0/oatpp")
message(STATUS "Include directories: ${CMAKE_INCLUDE_CURRENT_DIR}")

# 添加可执行文件
add_executable(main src/main.cpp)

# 链接 oatpp 库
target_link_libraries(main /usr/local/lib64/oatpp-1.3.0/liboatpp.a)
