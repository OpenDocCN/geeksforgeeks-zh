# Python NumPy np.flatiter()方法

> 原文: [https://www.geeksforgeeks.org/python-numpy-np-flatiter-method/](https://www.geeksforgeeks.org/python-numpy-np-flatiter-method/)

借助`np.flatiter()`方法，我们可以得到一个平面迭代器。

> **语法:** `np.flatiter()`
> **返回:** 返回平面迭代器。

## 示例 #1
在这个示例中，我们可以看到，通过使用`np.flatiter()`方法，我们能够获得平面迭代器。

```py
# import numpy
import numpy as np

# using np.flatiter() method
a = np.array([6, 5, 4, 3, 2, 1])
gfg = a.flat

for items in gfg:
    print(items)
```

**输出:**

> 6
> 5
> 4
> 3
> 2
> 1

## 示例 2

```py
# import numpy
import numpy as np

# using np.flatiter() method
a = np.array(['geeks', 'for', 'geeks'])
gfg = a.flat

for items in gfg:
    print(items)
```

**输出:**

> geeks
> for
> geeks