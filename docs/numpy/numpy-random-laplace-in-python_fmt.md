# Python 中的 `numpy.random.laplace()`

> 原文: [https://www.geeksforgeeks.org/numpy-random-laplace-in-python/](https://www.geeksforgeeks.org/numpy-random-laplace-in-python/)

借助 `numpy.random.laplace()` 方法，我们可以得到具有特定均值和尺度值的拉普拉斯或双指数分布的随机样本，并利用该方法返回随机样本。

![](img/00147f15ce006adb4b44239b8f8b8c59.png)

拉普拉斯分布

> **语法:** `numpy.random.laplace(loc=0.0, scale=1.0, size=None)`
> **返回:** 将随机样本作为 `numpy` 数组返回。

## 示例 1

在这个例子中，我们可以看到，通过使用 `numpy.random.laplace()` 方法，我们能够获得拉普拉斯或双指数分布的随机样本，并使用该方法返回随机样本。

```py
# import numpy
import numpy as np
import matplotlib.pyplot as plt

# Using numpy.random.laplace() method
gfg = np.random.laplace(1.45, 15, 1000)

count, bins, ignored = plt.hist(gfg, 30, density = True)
plt.show()
```

**输出:**

> ![](img/6fa4a58804dac3b5971bc0877cac7555.png)

## 示例 2

```py
# import numpy
import numpy as np
import matplotlib.pyplot as plt

# Using numpy.random.laplace() method
gfg = np.random.laplace(0.5, 12.45, 1000)
gfg1 = np.random.laplace(gfg, 12.45, 1000)

count, bins, ignored = plt.hist(gfg1, 40, density = True)
plt.show()
```

**输出:**

> ![](img/e477251ac25a4bd0c4126e8a5521df08.png)