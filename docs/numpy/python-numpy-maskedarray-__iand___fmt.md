# Python | Numpy MaskedArray.__iand__

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-num py-masked array-_ _ iand _/

`numpy.ma.MaskedArray`类是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助Numpy `MaskedArray.__iand__`，我们可以通过在MaskedArray中作为参数提供的值来获得and元素。`__iand__()`方法。

## 语法
`numpy.ma.MaskedArray.__iand__(self, value, /)`

## 返回
返回自身`&= value`。

## 示例#1
在这个示例中，我们可以看到每个元素都由作为参数在MaskedArray中传递的值进行and运算。`__iand__()`方法。

```py
# import the important module in python 
import numpy as np

# make an array with numpy 
gfg = np.ma.array([1, 2, 3, 4, 5])

# applying MaskedArray.__iand__() method 
print(gfg.__iand__(2))
```

**Output:**

```py
[0 2 2 0 0]
```

## 示例 2

```py
# import the important module in python 
import numpy as np

# make an array with numpy 
gfg = np.ma.array([[1, 2, 3, 4, 5], 
                [6, 5, 4, 3, 2]])

# applying MaskedArray.__iand__() method 
print(gfg.__iand__(1)) 
```

**Output:**

```py
[[1 0 1 0 1]
 [0 1 0 1 0]]
```