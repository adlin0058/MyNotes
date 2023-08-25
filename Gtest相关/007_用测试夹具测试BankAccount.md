# 用TEST_F测试BankAccount
---
### 包含文件
1. 003_BankAccount.cpp
   > 源文件构造了**BankAccount**类
2. 004_TEST_F.cc
   > 测试文件
     构造了测试夹具类**BankAccountTest**
        创建**BankAccount**类的对象**account**,并初始化属性**balance**的值为100.0

---
### 测试内容
1. 测试成员函数**getBalance**
   > 由于初始化balance为100.0
   account.getBalance()应为100.0
2. 测试成员函数**deposit**
   >account.deposit(50.0)后balance应为150.0
3. 测试成员函数**withdraw**正常
   >account.withdraw(50.0)应返回*true*
4. 测试成员函数**withdraw**异常
   >account.withdraw(50.0)应返回*false*

---
### 测试结果

```sh
[==========] Running 4 tests from 1 test suite.
[----------] Global test environment set-up.
[----------] 4 tests from BankAccountTest
[ RUN      ] BankAccountTest.getBalanceTest
[       OK ] BankAccountTest.getBalanceTest (0 ms)
[ RUN      ] BankAccountTest.depositTest
[       OK ] BankAccountTest.depositTest (0 ms)
[ RUN      ] BankAccountTest.withdrawSuccessedTest
[       OK ] BankAccountTest.withdrawSuccessedTest (0 ms)
[ RUN      ] BankAccountTest.withdrawFailedTest
[       OK ] BankAccountTest.withdrawFailedTest (0 ms)
[----------] 4 tests from BankAccountTest (0 ms total)

[----------] Global test environment tear-down
[==========] 4 tests from 1 test suite ran. (0 ms total)
[  PASSED  ] 4 tests.
```

---
### 完整项目
***003——BankAccount.cpp***
```cpp
#include <iostream>
using namespace std;

class BankAccount
{
public:
    // 结余
    double balance;

public:
    // 无参构造函数
    BankAccount() : balance(0.0) {}
    // 有参构造函数
    BankAccount(int balance) : balance(balance){};

    // 获取balance的值
    double getBalance() const
    {
        return balance;
    }
    // 存款函数
    void deposit(double amount)
    {
        balance += amount;
    }
    // 判断是否能取款
    bool withdraw(double amount)
    {
        if (amount <= balance)
        {
            balance -= amount;
            return true;
        }
        else
        {
            return false;
        }
    }
};

```

***004_TEST_F.cc***
```cpp
#include "003_BankAccount.cpp"
#include <gtest/gtest.h>

// 定义一个测试夹具类
class BankAccountTest : public testing::Test
{
protected:
    BankAccount account;
    void SetUp() override
    {
        // 初始化
        // 存款100.0
        // account.deposit(100.0);
        account.balance = 100.0;
    }
    // 清理
    // void TearDown() override{};
};

// 测试getBalance
TEST_F(BankAccountTest, getBalanceTest)
{
    double balance = account.getBalance();
    EXPECT_EQ(balance, 100.0);
}
// 测试deposit
TEST_F(BankAccountTest, depositTest)
{
    account.deposit(50.0);
    double balance = account.getBalance();
    EXPECT_EQ(150.0, balance);
}
// 测试withdraw取款成功
TEST_F(BankAccountTest, withdrawSuccessedTest)
{
    bool rst = account.withdraw(50.0);
    double balance = account.getBalance();
    EXPECT_TRUE(rst);
    EXPECT_EQ(balance, 50.0);
}
// 测试withdraw取款失败
TEST_F(BankAccountTest, withdrawFailedTest)
{
    bool rst = account.withdraw(200.0);
    double balance = account.getBalance();
    EXPECT_FALSE(rst);
    EXPECT_EQ(balance, 100.0);
}

// 测试入口
int main(int argc, char **argv)
{
    testing::InitGoogleTest(&argc, argv);
    return RUN_ALL_TESTS();
}
```