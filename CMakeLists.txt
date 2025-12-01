cmake_minimum_required(VERSION 3.10)
project(sift_demo)

#C++标准

#查找opencv
find_package(OpenCV REQUIRED)

#头文件搜索路径
include_directories(
    ${OpenCV_INCLUDE_DIRS}
    ${CMAKE_SOURCE_DIR}/src
    ${CMAKE_SOURCE_DIR}/src/sift
    )

#搜索所有cpp文件
file(GLOB_RECURSE SRC_FILES
    ${CMAKE_SOURCE_DIR}/src/*.cpp
    ${CMAKE_SOURCE_DIR}/src/sift/*.cpp
)

add_executable(sift_demo ${SRC_FILES})

target_link_libraries(sift_demo ${OpenCV_LIBS})
