# Python 中的 `numpy.compress()`

> 原文: [https://www.geeksforgeeks.org/numpy-compress-python/](https://www.geeksforgeeks.org/numpy-compress-python/)

`numpy.compress()` 函数返回沿所述轴的数组的选定切片，该切片满足一个轴。

```python
Syntax: numpy.compress(condition, array, axis = None, out = None)
```

## 参数

- `condition` : `[array_like]` 条件，用户根据此条件提取元素。将条件应用于 `input_array`，如果我们打印 `condition`，它将返回一个填充了 `True` 或 `False` 的数组。从值为 `True` 的索引处提取数组元素。
- `array` : 输入数组。用户对 `input_array` 元素应用条件。
- `axis` : `[optional, int]` 指示要选择的切片。默认情况下，作用于展平的数组（1-D）。
- `out` : `[optional, ndarray]` 输出数组，包含满足条件的 `input_array` 的元素。

## 返回

满足条件并沿给定轴的 `input_array` 元素的副本。

## 示例

```python
# Python Program illustrating
# numpy.compress method

import numpy as geek

array = geek.arange(10).reshape(5, 2)
print("Original array : \n", array)

a = geek.compress([0, 1], array, axis=0)
print("\nSliced array : \n", a)

a = geek.compress([False, True], array, axis=0)
print("\nSliced array : \n", a)
```

## 输出

```python
Original array : 
 [[0 1]
 [2 3]
 [4 5]
 [6 7]
 [8 9]]

Sliced array : 
 [[2 3]]

Sliced array : 
 [[2 3]]
```

## 参考文献
[https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.compress.html](https://docs.scipy.org/doc/numpy-dev/reference/generated/numpy.compress.html)

## 注
这些代码不会在 online-ID 上运行。请在您的系统上运行它们来探索工作。

本文由 **莫希特·古普塔 _OMG 供稿😀** 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。