[TOC]

# Python列表

## 追加元素

```python
list.append(item)
```

追加一个元素x到当前列表末尾。相当于`list[len(list):] = [item]` 。

## 扩展元素

```python
list.extend(L)
```

在当前列表末尾，追加另一个列表的内容。相当于`list[len(list): = L` 。

## 插入元素

```python
list.insert(index,item)
```

在当前列表，index下标处插入指定的元素。

`list.insert(len(list),item)` 相当于`list.append(item)`

## 移除元素

```python
list.remove(item)
```

移除当前列表中，第一个值为item的元素，若不存在item会报以下错误：

```python
ValueError: list.remove(item): item not in list
```

## 取出元素

```python
list.pop([index])
```

> 方括号“[]”代表选填的内容，并不是要打出方括号。

将当前列表，对应index下标的元素取出(返回值的同时remove掉)。

若不写下标，则`list.pop()`将取出最后一个元素。

## 清除元素

```python
list.clear()
```

清除当前列表中的所有元素。相当于`del list[:]`。

## 获取下标值

```python
list.index(item)
```

在当前列表中查找item，若存在item则返回item的下标值；若不存在，报以下错误：

```python
ValueError: 'x' is not in list
```

## 获得某元素出现的次数

```python
list.count(item)
```

在当前列表中查找item元素，并返回它出现的次数。若不存在item，返回0。

## 反转列表

```python
list.reverse()
```

将当前列表中的元素的排列顺序颠倒。

## 复制列表

```python
list.copy()
```

复制当前列表的值，并返回一个新的列表。相当于`a = b[:]` 。

## 列表的排序

```python
list.sort(key=None, reverse=False)
```

对当前列表的所有元素，返回一个排序后的新列表。



# 列表的应用

## 模拟Stack栈

使用append()入栈，pop()出栈。模拟先进后出。

## 模拟Queues队列

虽然内置的列表能够通过pop()第一个元素，来模拟队列的先进先出。但是效率很低，我们可以使用[`collections.deque`](../library/collections.html#collections.deque) 来实现队列。

```python
from collections import deque
queue = deque(["Cloud","Sen","Less"])
queue.append("Is") #在末尾追加IS
queue.popleft(); #取出当前第一个Cloud
queue.append("More") #在末尾追加More
queue.popleft(); #取出当前第一个Sen
输出：
deque(['Less', 'Is', 'More'])
```

## 列表推导

```python
[x for x in range(10)]
[x for x in range(10) if x%2==0]
[(x,y) for x in range(10) for y in range(10) if x%2==0 and y%2==0]
```

语法：

[如何显示x,y...n的值 关于x的for字句 关于y的for字句...关于n的for字句 if字句]

## 列表推导嵌套

