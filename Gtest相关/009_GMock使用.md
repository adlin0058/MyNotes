#GMOCK的使用

---
### 关于MOCK_METHOD


#### 定义
定义一个模拟方法，该方法可以接受任意数量和类型的参数，并返回任意类型的值


#### 如何使用
首先需要一个，定义一个类**MyMock**，而这个方法是这个类中的一个函数
**格式**
MOCK_METHOD1(myMethod,void(int a));
* 其中MOCK_METHOD**1**表示这个模拟方法有一个参数，
  同样的如果有两个参数使用MOCK_METHOD**2**
  以此类推，支持的参数上限为10个
* myMethod 为模拟函数名
* void 表示这个模拟函数的返回值类型
  可替换为 int ，char ，double等
* 返回值类型后的() 内是参数类型

**如MyMock类**
```cpp
class MyMock
{
public:
    MOCK_METHOD2(myMethod , void (int a,bool b));
}
```
**测试**
```cpp
TEST(MyMethodTest,Test1)
{
    MyMock mock;
    EXPECT_CALL(mock,myMethod(42,true));
    mock.myMethod(42,true);
}
```
--- 
### 关于EXPECT_CALL


#### 定义
设置一个期望，即模拟方法将以特定的参数被调用


#### 如何使用

EXPECT_CALL(mock,myMethod(42,true));
其中 mock 是对象名

---
### 完整样例
```cpp
#include <gtest/gtest.h>
#include <gmock/gmock.h>
#include <iostream>

class MyMock
{
public:
  MOCK_METHOD2(myMethod, void(int arg1, bool arg2));
};

TEST(MyMockTest, Test1)
{
  MyMock mock;
  EXPECT_CALL(mock, myMethod(42, true));
  mock.myMethod(42, true);
}

int main(int argc, char **argv)
{
  testing::InitGoogleTest(&argc, argv);
  return RUN_ALL_TESTS();
}

```