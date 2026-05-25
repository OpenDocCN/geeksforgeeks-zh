# ndarray.__ixor__()

> 原文链接：[https://www.geeksforgeeks.org/python-numpy-ndarray-__ixor__/](https://www.geeksforgeeks.org/python-numpy-ndarray-__ixor__/)

借助`ndarray.__ixor__()`方法，我们可以通过该方法中作为参数提供的值得到数组元素异或（XOR）的结果。

**语法：**
`ndarray.__ixor__(self, value, /)`

**返回：**
`self ^= value`

## 示例 1

在这个示例中，我们可以看到数组中的每个元素都与作为参数传递给`ndarray.__ixor__()`方法的值进行了异或。

```python
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, 2, 3, 4, 5])

# applying ndarray.__ixor__() method
print(gfg.__ixor__(2))
```

**输出：**

```python
[3 0 1 6 7]
```

## 示例 2

```python
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying ndarray.__ixor__() method
print(gfg.__ixor__(1))
```

**输出：**

```python
[[0 3 2 5 4]
 [7 4 5 2 3]]
```