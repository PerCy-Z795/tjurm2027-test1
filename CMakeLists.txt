cmake_minimum_required(VERSION 3.10)
project(tjurm2027-test1 LANGUAGES CXX)

# 使用 C++11 标准
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# 默认使用 Release 构建类型
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release)
endif()

# 可执行目标：tjurm-test
add_executable(tjurm-test
    main.cpp
    src/tests.cpp
    src/utils.cpp
)

# 头文件搜索路径：项目根目录（main.cpp 用 "include/utils.h"）+ include 目录
target_include_directories(tjurm-test PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)

# 编译选项：-w 关闭警告，-O3 优化，-g 保留调试信息
target_compile_options(tjurm-test PRIVATE -w -O3 -g)
