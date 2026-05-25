# Matplotlib.pyplot.grid() 中的 Python

## matplotlib.pyplot.grid() 函数

matplotlib 库 pyplot 模块中的 `grid()` 函数用于配置网格线。

> **语法:** `matplotlib.pyplot.grid(b=None, which='major', axis='both', **kwargs)`
>
> **参数:** 该方法接受以下参数。
>
> *   `b`: 该参数为可选参数，是否显示网格线。
> *   `which`: 这个参数也是可选参数，是要应用更改的网格线。
> *   `axis`: 该参数也是可选参数，是应用更改的轴。
>
> **返回:** 该方法不返回值。

下面的例子说明了 `matplotlib.pyplot.grid()` 函数在 `matplotlib.pyplot` 中的作用:

### 示例 #1

```py
# Implementation of matplotlib function   
import matplotlib.pyplot as plt
import numpy as np

plt.plot([1, 2, 3])
plt.grid()

plt.title('matplotlib.pyplot.grid() function \
Example\n\n', fontweight ="bold")
plt.show()
```

**输出:**
![](img/8a1c1f596dab6d055947aa4a390e34de.png)

### 示例 #2

```py
# Implementation of matplotlib function   
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(19680801)

val, res = 100, 15
x = np.sin(val + res * np.random.randn(10000)) - np.cos(val + res * np.random.randn(10000))

n, bins, patches = plt.hist(x, 200, 
                            density = True, 
                            facecolor ='g', 
                            alpha = 0.5)

plt.grid(True)

plt.title('matplotlib.pyplot.grid() function \
Example\n\n', fontweight ="bold")

plt.show()
```

**输出:**
![](img/719ad170aa8e32d0b5abdec8b023050e.png)