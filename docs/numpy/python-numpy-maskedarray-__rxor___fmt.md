# NumPy 掩码数组：`MaskedArray.__rxor__` 方法

`numpy.ma.MaskedArray class` 是 `ndarray` 的一个子类，设计用于处理缺少数据的数值数组。借助 NumPy 的 `MaskedArray.__rxor__` 方法，我们可以得到与作为参数提供的值进行异或的元素。

## 语法

`numpy.ma.MaskedArray.__rxor__(self, value, /)`

**返回：** 返回 `value ^ self`。

## 示例

### 示例 1

在这个示例中，我们可以看到每个元素都与作为参数传递的值进行异或。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([1, 2, 3, 4, 5])

# applying MaskedArray.__rxor__() method
print(gfg.__rxor__(2))
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

# applying MaskedArray.__rxor__() method
print(gfg.__rxor__(1))
```

**输出：**

```py
[[0 3 2 5 4]
 [7 4 5 2 3]]
```