# Python | Numpy MaskedArray

`numpy.ma.MaskedArray class`是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助Numpy `MaskedArray.__pow__`方法我们可以使用作为参数提供的值为元素供电。

## 语法
`numpy.ma.MaskedArray.__rpow__()`

## 返回
将他者提升至力量自性，遮蔽潜在的`NaNs`。

## 示例 #1
在这个示例中，我们可以看到在应用`MaskedArray.__rpow__()`之后，我们可以看到每个元素都以作为参数提供的值为动力。

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([1, 2, 3, 4, 5])

# applying MaskedArray.__rpow__() method
print(gfg.__rpow__(3))
```

**Output:**

```py
[  3   9  27  81 243]
```

## 示例 2

```py
# import the important module in python
import numpy as np

# make an array with numpy
gfg = np.ma.array([[1, 2, 3, 4, 5],
                [6, 5, 4, 3, 2]])

# applying MaskedArray.__pow__() method
print(gfg.__pow__(2))
```

**Output:**

```py
[[ 1  4  9 16 25]
 [36 25 16  9  4]]
```