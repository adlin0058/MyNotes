// Google Mock 实例1
#include <gtest/gtest.h>
#include <gmock/gmock.h>

// 定义一个模拟类
class MyMock
{
public:
    // 模拟函数
    MOCK_METHOD2(myMethod, void(int a, int b));
};

TEST(MyMockTest, myMethodTest)
{
    // 实例化一个对象
    MyMock mock;
    EXPECT_CALL(mock, myMethod(10, 20));
    mock.myMethod(10, 20);
}

int main(int argc, char **argv)
{
    testing::InitGoogleTest(&argc, argv);
    return RUN_ALL_TESTS();
}