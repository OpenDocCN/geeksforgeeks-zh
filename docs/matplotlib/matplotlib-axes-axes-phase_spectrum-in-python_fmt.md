# matplotlib.axes.Axes.phase_spectrum()

> 原文：[https://www.geeksforgeeks.org/matplotlib-axes-axes-phase_spectrum-in-python/](https://www.geeksforgeeks.org/matplotlib-axes-axes-phase_spectrum-in-python/)

`Matplotlib` 是 Python 中的一个库，是 `NumPy` 库的数值-数学扩展。`Axes` 类包含了大部分的图形元素：轴、刻度、`Line2D`、文本、多边形等，并设置坐标系。`Axes` 的实例通过回调属性支持回调。

## matplotlib.axes.Axes.phase_spectrum() 函数

`matplotlib` 库的 `Axes` 模块中的 `Axes.phase_spectrum()` 函数用于绘制相谱。

> **语法：** `Axes.phase_spectrum(self, x, Fs=None, Fc=None, window=None, pad_to=None, sides=None, *, data=None, **kwargs)`
>
> **参数：** 该方法接受以下描述的参数：
>
> *   `x`：这个参数是一个数据序列。
> *   `Fs`：此参数为标量。它的默认值是 `2`。
> *   `window`：该参数以一个数据段为自变量，返回该段的窗口版本。其默认值为 `window_hanning()`。
> *   `sides`：此参数指定要返回光谱的哪些边。这可以有以下值：`'default'`、`'onesided'` 和 `'twosided'`。
> *   `pad_to`：此参数包含数据段填充到的整数值。
> *   `Fc`：该参数还包含偏移绘图 x 范围的整数值，以反映频率范围。其默认值为 `0`。
>
> **返回：** 这将返回以下内容：
>
> *   `spectrum`：以弧度为单位返回角度光谱。
> *   `freqs`：返回频谱中元素对应的频率。
> *   `line`：返回该函数创建的线。
>
> 结果是 `(spectrum, freqs, line)`。

下面的例子说明了 `matplotlib.axes.Axes.phase_spectrum()` 函数在 `matplotlib.axes` 中的作用：

**例 1：**

```py
# Implementation of matplotlib function
import matplotlib.pyplot as plt
import numpy as np
np.random.seed(10**5)

dt = 0.0001
Fs = 1 / dt
geeks = np.array([22.00, 61.90, 7.80,
                  24.40, 110.25, 20.05,
                  15.00, 22.80, 34.90,
                  57.30])

nse = np.random.randn(len(geeks))
r = np.exp(-geeks / 0.05)

s = 0.5 * np.sin(1.5 * np.pi * geeks) + nse

# plot phase_spectrum
fig, ax = plt.subplots()
ax.phase_spectrum(s, Fs = Fs, color ="green")

ax.set_title('matplotlib.axes.Axes.phase_spectrum()\
Example')

plt.show()
```

**输出：**
![](img/c3d17d904222dd1006639412dae4ecf0.png)

**例 2：**

```py
# Implementation of matplotlib function
import matplotlib.pyplot as plt
import numpy as np
np.random.seed(0)

dt = 0.01
Fs = 1 / dt
t = np.arange(0, 10, dt)
res = np.random.randn(len(t))
r = np.exp(-t / 0.05)

cres = np.convolve(res, r)*dt
cres = cres[:len(t)]
s = 0.5 * np.sin(1.5 * np.pi * t) + cres

# plot simple spectrum
fig, (ax1, ax2) = plt.subplots(2, 1)
ax1.plot(t, s, color ="green")

# plot phase_spectrum
ax2.phase_spectrum(s, Fs = Fs, color ="green")

ax1.set_title('matplotlib.axes.Axes.phase_spectrum()\
Example')

plt.show()
```

**输出：**
![](img/c4122570173b8517674fe36a2fc60216.png)