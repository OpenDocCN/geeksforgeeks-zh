# NumPy MaskedArray.__lshift__()方法

> 原文链接：[https://www.geeksforgeeks.org/python-numpy-maskedarray-__lshift__/](https://www.geeksforgeeks.org/python-numpy-maskedarray-__lshift__/)

`numpy.ma.MaskedArray`类是`ndarray`的一个子类，设计用于处理缺少数据的数值数组。借助NumPy `MaskedArray.__lshift__()`方法，我们可以得到左移了作为参数提供的值的元素。

## 语法

`numpy.ma.MaskedArray.__lshift__()`

## 返回值

返回自身左移`值`后的结果。

## 示例1

在这个示例中，我们可以看到每个元素都被作为参数传递的值向左移动了。

```python
# import the important module in python 
import numpy as np

# make an array with numpy 
gfg = np.ma.array([1, 2, 3, 4, 5])

# applying MaskedArray.__lshift__() method 
print(gfg.__lshift__(2)) 
```

**输出：**

```python
[ 4  8 12 16 20]
```

## 示例2

```python
# import the important module in python 
import numpy as np

# make an array with numpy 
gfg = np.ma.array([[1, 2, 3, 4, 5], 
                [6, 5, 4, 3, 2]])

# applying MaskedArray.__lshift__() method 
print(gfg.__lshift__(1)) 
```

**输出：**

```python
[[ 2  4  6  8 10]
 [12 10  8  6  4]]
```