# Python中的`numpy.random.noncentral_chisquare()`

> 原文: [https://www.geeksforgeeks.org/numpy-random-noncentral_chisquare-in-python/](https://www.geeksforgeeks.org/numpy-random-noncentral_chisquare-in-python/)

借助`numpy.random.noncentral_chisquare()`方法，可以得到非中心卡方分布的随机样本，并利用该方法返回其随机样本。

![](img/fcf4a848a5293be62b0a1f76e8676e85.png)

非中心卡方分布

## 语法

`numpy.random.noncentral_chisquare(df, nonc, size=None)`

## 返回

将随机样本作为`numpy`数组返回。

## 示例 #1

在这个例子中我们可以看到，通过使用`numpy.random.noncentral_chisquare()`方法，我们能够获得非中心卡方分布的随机样本，并使用该方法返回随机样本。

```py
# import numpy
import numpy as np
import matplotlib.pyplot as plt

# Using noncentral_chisquare() method
gfg = np.random.noncentral_chisquare(1.21, 9.89, 1000)

count, bins, ignored = plt.hist(gfg, 30, density = True)
plt.show()
```

**输出:**

> ![](img/820a1648acfaee32a490a9270a66119f.png)

## 示例 2

```py
# import numpy
import numpy as np
import matplotlib.pyplot as plt

# Using noncentral_chisquare() method
gfg = np.random.noncentral_chisquare(14.05, 3.24, 3000)

count, bins, ignored = plt.hist(gfg, 14, density = True)
plt.show()
```

**输出:**

> ![](img/3ffed5c270ac3564d471fe41d78ceffd.png)