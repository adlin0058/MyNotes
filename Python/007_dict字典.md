# dict
- dict全称dictionary，
- 在其他语言中也称为map，
- 使用键-值（key-value）存储，
- 具有极快的查找速度。

### 使用
```py
d = {'Michael':95,'Bob':75,'Tracy':85}
print(d['Michael'])

# 修改value
d['Bob'] = 80
print(d['Bob'])

# 判断key是否存在
print('Thomas' in d)

#get()方法，如果key不存在，返回None
d.get('Thomas')
#可以自定义返回值
d.get('Thomas',-1)#key不存在时返回-1

# 删除一个key，pop(key)方法
d.pop('Bob')
print(d)
```
### 注意
- dict内部存放的顺序和key放入的顺序是没有关系的
- 和list比较，dict有以下几个特点:
  1. 查找和插入的速度极快，不会随着key的增加而变慢
  2. 需要占用大量的内存，内存浪费多
- 而list相反
  1. 查找和插入的时间随着元素的增加而增加
  2. 占用空间小，浪费内存很少
- dict是用空间来换取时间的一种方法
- dict 的key必须是**不可变对象**
- Python中 字符串、整数 都是不可变的