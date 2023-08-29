### 打印
```py
print('hello world')
print(123)
print(100 + 100)
print(2**10)
print('100 + 200 =',100 + 200)
```

### 输入 input
```py
# input()默认输入字符串
name = input()
print('you are so nice',name)

a = int(input())# 将输入转换为整数
```

### 条件语句
```py
a = 100
if a >= 0:
    print(a)
else:
    print(-a)
```

### 变量类型
```py
a = 100 #整数
b = 37.23 #浮点数
c = 'hello' #字符串
True
False #布尔类型

# 特殊计数法
d = 10_000_000_000
e = 0x8d2e_2c9a
f = 1.23e9
g = -78.21

# 转义字符
print('I\'m OK.')

# 使转义字符失效
print(r'\\\t\\')

# 多行打印
print(r'''line1
line2
line3''')
```

