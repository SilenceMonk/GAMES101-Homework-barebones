cmake_minimum_required(VERSION 3.10)
project(Rasterizer)

# Tell CMake to find BOTH required packages
find_package(OpenCV REQUIRED)
find_package(Eigen3 REQUIRED)

set(CMAKE_CXX_STANDARD 17)

# Add the include directories for BOTH packages
# CMake will now know where to find <opencv2/opencv.hpp> AND <eigen3/Eigen/Eigen>

add_executable(Rasterizer main.cpp rasterizer.hpp rasterizer.cpp Triangle.hpp Triangle.cpp)

# Link the libraries needed by the executable
target_link_libraries(Rasterizer ${OpenCV_LIBRARIES} Eigen3::Eigen)
