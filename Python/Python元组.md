[TOC]

# Tuple元组

> A tuple consists of a number of values separated by commas
>
> - Tuples may be nested;
> - Tuples are immutable,but they can contain mutable objects, such as lists;

> Tuples are immutable, and usually contain an heterogeneous sequence of elements that are accessed via unpacking (see later in this section) or indexing (or even by attribute in the case of namedtuples).
>
>  Lists are mutable, and their elements are usually homogeneous and are accessed by iterating over the list.

## 定义

- 元组由多个元素构成，它们之间使用逗号隔开

  元组输出时，会被圆括号所包围，如：

  ```python
  In [1]: mytuple=7355,608,"leet" #定义一个元组
  In [2]: mytuple
  Out[2]: (7355, 608, 'leet')
      
  In [3]: (mytuple,(7,3,5,5,6,0,8)) #元组的嵌套
  Out[3]: ((7355, 608, 'leet'), (7, 3, 5, 5, 6, 0, 8))
  ```

- 定义空元组

  空元组由一对圆括号构成：

  ```python
  In [1]: emptyTuple = ()
  In [2]: emptyTuple
  Out[2]: ()
  ```

- 定义只含一个元素的元组

  在元素后面添加一个逗号：

  ```python
  In [1]: singleDog = "gf",
  In [2]: singleDog
  Out[2]: ('gf',)
  ```

## Tuple的使用

### Tuple Packing 元组的打包

通过逗号将一系列的值分隔开来，一并打包为一个元组，就叫元组打包。定义元组时，就是一个打包的操作。

### Tuple UnPacking 元组的解包

将一个元组反向赋值给一系列的变量，就是一个解包的操作。

将元组中的值，依次赋值给左侧的变量。如：

```python
In [1]: tuple = "Give","Me","Half-Life",3
In [2]: w,x,y,z = tuple
In [3]: print(w,x,y,z)
Give Me Half-Life 3
```

### 读取元组的值

元组的值可以通过下标读取，如：

```python
In [1]: answer = (4,'2')
In [2]: answer[0]
Out[2]: 4
In [3]: answer[1]
Out[3]: '2'
In [4]: answer[-1]
Out[4]: '2'
In [5]: answer[-2]
Out[5]: 4
In [6]: answer[2]
IndexError: tuple index out of range
```

元组中的基本类型元素，是无法被改变的。

但是我们可以在元组中放入可变元素(引用)，对可变元素的值进行操作(地址始终未变)。

如：

```python
In [1]: list = [1,3,3,7]
In [2]: list2 = [7,3,3,1]
In [3]: tuple = (list,'l','e',3,7)
In [4]: tuple
Out[4]: ([1, 3, 3, 7], 'l', 'e', 3, 7)
In [5]: tuple[1] = 's' #基本类型无法改动
TypeError: 'tuple' object does not support item assignment
In [6]: tuple[0].extend(list2) #但是可以改变可变元素的值
In [7]: tuple
Out[7]: ([1, 3, 3, 7, 7, 3, 3, 1], 'l', 'e', 3, 7)
```

如：

```python
In [1]: a = [3,5,1,"sf"]
In [2]: b = [7,2,'3',6]
In [3]: tuple = (a,6,8,"sfs")
In [4]: tuple2 = (tuple,0,0,'h')
In [5]: tuple2
Out[5]: (([3, 5, 1, 'sf'], 6, 8, 'sfs'), 0, 0, 'h')
In [6]: tuple2[0][0].remove(5)
In [7]: tuple2
Out[7]: (([3, 1, 'sf'], 6, 8, 'sfs'), 0, 0, 'h')
```

