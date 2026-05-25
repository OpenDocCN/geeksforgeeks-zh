# numpy.ndarray.__pos__()

> 哎哎哎:# t0]https://www.geeksforgeeks.org/python-numpy-numpy-ndaarray-__pos__/

借助`Numpy`的`numpy.ndarray.__pos__()`方法，可以将数组中的每个元素乘以 1。因此，结果数组的值与原始数组的值相同。

**语法:**
`numpy.ndarray.__pos__($self, /)`

**返回:**
`+self`

## 示例

### 示例 1
在这个示例中我们可以看到，应用`numpy.__pos__()`后，我们得到了和原来一样的简单数组。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([1, -2, 3, 4, 5, 6])

# applying numpy.__pos__() method
print(gfg.__pos__())
```

**Output:**

```py
[ 1 -2  3  4  5  6]
```

### 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.array([[1, 2, -3, 4, 5, 6],
                [-6, 5, 4, 3, 2, -1]])

# applying numpy.__pos__() method
print(gfg.__pos__())
```

**Output:**

```py
[[ 1  2 -3  4  5  6]
 [-6  5  4  3  2 -1]]
```