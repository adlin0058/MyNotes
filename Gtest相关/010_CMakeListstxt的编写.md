# CMakeLists.txt

### CMake最低版本号要求
```php
cmake_minimum_required(VERSION 3.10)
```
### 项目信息
```php
project(gtestdemo)
```
### 包含头文件
```php
link_directories(/usr/local/lib)
include_directories(/usr/local/include)
find_package(gtest )
find_package(gmock)
# find_package(pthread)
```
### 指定生成目标
```php
add_executable(gtest1 gtest1.cpp)
target_link_libraries(gtest1 gtest pthread)

```

---
### 适用于gtest/gmock的CMakeList.txt
```php
cmake_minimum_required(VERSION 3.10)

project(gtestdemo)
link_directories(/usr/local/lib)
include_directories(/usr/local/include)
find_package(gtest )
find_package(gmock)
# find_package(pthread)

add_executable(gtest1 gtest1.cpp)
target_link_libraries(gtest1 gtest pthread)

add_executable(gtest2 gtest2.cpp)
target_link_libraries(gtest2 gtest pthread)


add_executable(gtest3 gtest3.cpp)
target_link_libraries(gtest3 gtest pthread)

add_executable(gtest4 gtest4.cpp)
target_link_libraries(gtest4 gtest pthread)

add_executable(gtest5 gtest5.cpp)
target_link_libraries(gtest5 gmock gtest pthread)

add_executable(gtest6 gtest6.cpp)
target_link_libraries(gtest6 gmock gtest pthread)

add_executable(gtest7 gtest7.cpp)
target_link_libraries(gtest7 gmock gtest pthread)
```