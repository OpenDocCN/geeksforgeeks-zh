# 如何修复：“numpy.ndarray”对象没有属性“index”

> 原文：[https://www.geeksforgeeks.org/how-to-fix-numpy-ndarray-object-has-no-attribute-index/](https://www.geeksforgeeks.org/how-to-fix-numpy-ndarray-object-has-no-attribute-index/)

`numpy.ndarray`对象没有属性`index`是一个属性错误，表示在`Numpy`数组中没有`index`方法或属性可用。

当我们尝试使用`index`方法在`Numpy`数组中查找特定元素的索引时，会出现此错误。下面代码是一个示例，当`numpy.ndarray`对象没有`index`属性时，会引发错误。

## 例

```py
# import necessary packages
import numpy as np

# Create a Numpy array
numbers = np.array([0, 1, 2, 9, 8, 0])

# finding the index value of 9 in
# numbers array
numbers.index(9)
```

**输出**

![](img/5760ee53e40e77fc28310a664309e42d.png)

由于`Numpy`中没有名为`index`的方法，因此会引发属性错误。

## 解决办法

要修复此错误，不要使用`index`方法来查找元素的索引，使用`where`方法，它返回一个数组，该数组由指定元素的索引组成。

**语法**

```py
numpy.where(Arrayname == value_to_find_index)
```

### 例 1

指定`Numpy`数组中存在的`where`方法中的元素。

```py
# import necessary packages
import numpy as np

# Create a Numpy array
numbers = np.array([0, 1, 2, 9, 8, 0])

# finding the index value of 9 in
# numbers array
np.where(numbers == 9)
```

**输出**

```py
(array([3], dtype=int64),)
```

由于数组中的索引从 0 开始，因此在`numbers`数组中，第 0 索引由值 0 占据，第 1 索引具有值 1，第 2 索引具有值 2，第 3 索引具有值 9。

### 例 2

在`where`方法中指定一个元素，该元素在数组中出现多次。

```py
# import necessary packages
import numpy as np

# Create a Numpy array
numbers = np.array([0, 1, 2, 9, 8, 0])

# finding the index values of 0 in
# numbers array
np.where(numbers == 0)
```

**输出**

```py
(array([0, 5], dtype=int64),)
```

由于元素 0 在`numbers`数组中出现 2 次（在第 0 和第 5 索引处），因此它返回一个由元素 0 的 2 个索引值组成的数组。

### 例 3

将实际上不在数组中的元素传递给`where`方法。

```py
# import necessary packages
import numpy as np

# Create a Numpy array
numbers = np.array([0, 1, 2, 9, 8, 0])

# finding the index value of a number
# which is not in numbers array
np.where(numbers == 7)
```

**输出**

```py
(array([], dtype=int64),)
```

如果我们将一个不在数组中的元素传递给`where`方法，那么它将返回一个空数组，因为在数组的任何索引处都没有指定的元素。这里 7 在`numbers`数组中不存在，所以它返回了一个空数组。