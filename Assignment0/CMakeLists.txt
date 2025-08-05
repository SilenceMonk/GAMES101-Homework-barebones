# 使用一个更新的CMake版本，这能更好地支持现代CMake特性
cmake_minimum_required(VERSION 3.10)
project(Transformation)

# 寻找Eigen3包，这是关键
find_package(Eigen3 REQUIRED)

# 添加可执行文件
add_executable(Transformation main.cpp)

# 将Eigen3链接到你的目标上。
# 这是现代CMake的写法，它会自动设置包含目录和其它需要的属性。
# "Eigen3::Eigen" 是Eigen3提供的一个"IMPORTED target"。
target_link_libraries(Transformation PRIVATE Eigen3::Eigen)
