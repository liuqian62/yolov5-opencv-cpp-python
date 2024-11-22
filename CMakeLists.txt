cmake_minimum_required(VERSION 3.3)
project(yolov5cpp)

# 设置 C++ 标准  
set(CMAKE_CXX_STANDARD 11)  
set(CMAKE_CXX_STANDARD_REQUIRED ON)  

# 设置优化级别为 O3  
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3")  

# 替换下面的路径为您的 OpenCV build 目录  
set(OpenCV_DIR "/home/lirich/third/opencv-4.5.5/build")  
# 查找 OpenCV 包  
find_package(OpenCV 4.5 REQUIRED)  

# 添加可执行文件  
add_executable(yolo_example cpp/yolo.cpp)  

# 链接 OpenCV 库  
target_link_libraries(yolo_example PRIVATE ${OpenCV_LIBS})  

# 包含 OpenCV 头文件目录  
target_include_directories(yolo_example PRIVATE ${OpenCV_INCLUDE_DIRS})


