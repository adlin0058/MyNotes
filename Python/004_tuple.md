### tuple
**定义**
元组 ， 与list非常相似，可以像list一样访问元素
如：
```py
classmates[0],classmates[-1]
```

**区别**
tuple一旦初始化就不能修改,不能使用append(),insert()这样的方法

**意义**
tuple不可变，代码更安全
如果可能，尽可能使用tuple

**注意**
- 在定义一个tuple时，tuple的元素必须被定义下来
  ```py
  t = (1,2)
  ```
- 定义一个空的tuple
  ```py
  t = ()
  ```
- tuple只有一个元素时，定义时必须加一个“，”
  ```py
  t = (1,)
  ```
- tuple可以包含list
  ```py
  T = ('a','b',['A','B'])
  ```
- tuple的不变，指的是tuple每个元素的指向不会改变，但是指向的元素可以改变
  ```py
  T[2][0] = 'X'
  T[2][1] = 'Y'
  ```