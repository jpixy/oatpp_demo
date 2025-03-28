# cmake_minimum_required(VERSION 3.10)
# project(oatpp_demo)

# # 设置 C++ 标准
# set(CMAKE_CXX_STANDARD 17)
# set(CMAKE_CXX_STANDARD_REQUIRED True)

# # 包含 oatpp 的头文件路径
# include_directories("/usr/local/include/oatpp-1.3.0/oatpp")
# message(STATUS "Include directories: ${CMAKE_INCLUDE_CURRENT_DIR}")

# # 添加可执行文件
# add_executable(main src/main.cpp)

# # 链接 oatpp 库
# target_link_libraries(main /usr/local/lib64/oatpp-1.3.0/liboatpp.a)


set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(oatpp_demo src/main.cpp)

# 设置头文件路径
set(OATPP_INCLUDE_DIR "/usr/local/include/oatpp-1.3.0/oatpp")
message(STATUS "Include directories: ${OATPP_INCLUDE_DIR}")
target_include_directories(oatpp_demo PRIVATE ${OATPP_INCLUDE_DIR})

# 设置库文件路径
set(OATPP_LIB_DIR "/usr/local/lib64/oatpp-1.3.0")
target_link_libraries(oatpp_demo PRIVATE ${OATPP_LIB_DIR}/liboatpp.a)

# 安装目标
include(GNUInstallDirs)
install(TARGETS oatpp_demo
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)