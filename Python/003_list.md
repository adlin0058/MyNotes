### list
- Python 内置的一种数据类型列表
- 使用方法
  ```py
  classmates = ['Michael','Bob','Tracy']
  # 打印整个列表元素
  print(classmates)
  # 打印第一个元素
  print(classmates[0])
  # 打印倒数第一个元素
  print(classmates[-1])
  # 倒数第二个
  print(classmates[-2])
  ```
- 在尾部添加元素
  list是一个可变的有序表
  向list中追加元素到末尾
  ```py
  classmates.append('Adam')
  print(classmates)
  ```
- 将元素插入到指定位置
  ```py
  # 将'Jack'插入到索引位置为1的位置
  classmates.insert(1,'Jack')
  ```
- 删除list尾部元素
  ```py
  # 删除尾部元素
  classmates.pop()
  ```
- 删除指定位置元素
  ```py
  # 删除索引位置为1的元素
  classmates.pop(1)
  ```
- 替换元素
  ```py
  classmates[1] = 'Sarah'
  ```
- list里面的元素数据类型可能不同
  ```py
  L = ['Apple',123,True]
  ```
- list里的元素也可以是另一个list
  ```py
  s = ['python','java',['asp','php'],'scheme']
  ```
- 二维
  ```py
  p = ['asp','php']
  s = ['python','java',p,'scheme']
  ```
  要拿到'php'可以写'p[1]'或者s[2][1]
- list里一个元素也没有，为空list，长度为0
  ```py
  L = []
  len(L) == 0
  ```