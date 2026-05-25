# Python Numpy MaskedArray

## 介绍

`numpy.ma.MaskedArray`类是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助Numpy的`MaskedArray.__xor__`方法，我们可以通过作为参数提供的值得到**XOR**（异或）的元素。

## 语法

`numpy.ma.MaskedArray.__xor__(self, value, /)`

**返回：** 返回`self ^ value`。

## 示例

### 示例 1

在这个示例中，我们可以看到每个元素都与作为参数传递的值进行异或。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([1, 2, 3, 4, 5])

# applying MaskedArray.__xor__() method
print(gfg.__xor__(2))
```

**输出：**

```py
[3 0 1 6 7]
```

### 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[1, 2, 3, 4, 5],
                   [6, 5, 4, 3, 2]])

# applying MaskedArray.__xor__() method
print(gfg.__xor__(1))
```

**输出：**

```py
[[0 3 2 5 4]
 [7 4 5 2 3]]
```