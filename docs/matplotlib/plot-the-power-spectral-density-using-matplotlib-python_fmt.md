# 使用 Matplotlib–Python 绘制功率谱密度图

> 原文: [https://www.geeksforgeeks.org/plot-the-power-spectral-density-using-matplotlib-python/](https://www.geeksforgeeks.org/plot-the-power-spectral-density-using-matplotlib-python/)

`matplotlib.pyplot.psd()` 函数用于绘制功率谱密度。在用于评估功率谱密度的韦尔奇平均周期图方法中(例如，`P_{xx}`，向量`x`被平均分成 `NFFT` 段。每个片段都由函数窗口加窗，并由函数去趋势化去趋势。线段之间的重叠由`noverlap`表示。每个段`i`的`|fft(i)|^2`被一起平均以计算 `P`，并带有缓冲缩放以校正由于开窗导致的功率损失。

**注:** 若 `len(x) < NFFT`，则 `NFFT` 填充为零。

> **语法:** `matplotlib.pyplot.psd(x, NFFT=None, Fs=None, Fc=None, detrend=None, window=None, noverlap=None, pad_to=None, sides=None, scale_by_freq=None, return_line=None, *data, **kwargs)`
>
> **参数:**
>
> 1.  **x:** 是 1D 阵列或含有数据的序列的必要参数。
> 2.  **Fs:** 这是一个必需参数，具有标量值，默认值为 2。它的值是采样频率(每时间单位的样本数)。该值用于计算单位时间内以周期为单位的傅里叶频率。
> 3.  **window:** 这是一个可调用的 N-D 数组，一般是 `NFFT` 长度的函数或向量。它的默认值是 `window_hanning`。当函数作为参数/自变量传递时，它将数据段作为自变量，并返回该段的窗口版本。
> 4.  **sides:** 该参数可以有三个值之一，即`'default'`、`'onesided'`或`'twosided'`。这用于指定要返回光谱的哪一面。`'default'`给出了它的默认行为，对于真实数据和复杂数据都返回单侧。`'onesided'`值用于强制返回单侧光谱，而`'twosided'`值用于返回双侧光谱。
> 5.  **pad_to:** 此参数保存一个整数值，表示执行 FFT 时数据段被填充的点数。需要注意的是，这与 `NFFT` 不同，后者设置使用的数据点数量。这可以在图上给出更多的点，而不会增加光谱的实际分辨率(可分辨峰之间的最小距离)，从而允许更多的细节。这也对应于 `fft()` 调用中的`n`参数。其默认值为`None`，将 `pad_to` 设置为等于 `NFFT`。
> 6.  **NFFT:** 它保存一个整数值，代表每个块中用于 FFT 的数据点数。效率最高的是 2 的幂。它的默认值是 256。必须避免使用它来获得零填充，因为它可能导致结果的不正确缩放，相反，`pad_to` 将用于相同的目的。
> 7.  **detrend:** 它可以接受三个值，即`None`、`'mean'`、`'linear'`或可调用，默认值为`None`。这个函数被设计成在对每个分段进行 fft 之前去除平均值或线性趋势。Matplotlib 中的去趋势是一个函数，不像 MATLAB 中的去趋势是一个向量。`detrend_none`、`detrend_mean`和`detrend_linear`是由 `mlab` 模块定义的，但是也可以使用自定义函数。字符串也可以选择一个函数。`'none'`调用`detrend_none`，`'linear'`调用`detrend_linear`，而`'mean'`调用`detrend_mean`。
> 8.  **scale_by_freq:** 它是接受布尔值的可选参数。它用于指定是否应该通过缩放频率来缩放生成的密度。这将给出以 `Hz^-1` 为单位的密度，这使得对返回的频率值进行积分。MATLAB 兼容性的默认值为 `True`。
> 9.  **noverlap:** 它是一个整数值，表示线段之间重叠的总点数。默认值为 0，表示没有重叠。
> 10. **Fc:** 它是一个整数值，表示曲线 x 范围的偏移，以反映获得信号并滤波后将其下采样到基带时使用的频率范围。`x` 代表 `x` 的中心频率(默认值为 0)。
> 11. **return_line:** 是一个布尔值，它决定是否在返回值中包含绘制的对象线。默认情况下，该值为 `False`。
>
> **返回:**
>
> 1.  **P_{xx}:** 它是一个一维数组，表示缩放前的功率谱 `P_{xx}`。
> 2.  **freqs:** 是一个 1-D 数组，表示对应于 `P_{xx}` 元素的频率。
> 3.  **line:** 是 `Line2D` 实例，是函数生成的一行。只有当 `return_line` 设置为 `True` 时，它才会返回。

**其他参数:**
`**kwargs` 关键字参数用于控制 `Line2D` 属性。

| 属性 | 描述 |
| --- | --- |
| `agg_filter` | 接受 `(m, n, 3)` 浮点数组和返回 `(m, n, 3)` 数组的 dpi 值的筛选函数 |
| `alpha` | 浮点数 |
| `animated` | 布尔值 |
| `antialiased` 或 `aa` | 布尔值 |
| `clipbox` | `Bbox` |
| `clip_on` | 布尔值 |
| `clip_path` | `[(Path, Transform) | Patch | None]` |
| `color` 或 `c` | 颜色 |
| `contains` | 可调用 |
| `dash_capstyle` | `{'butt', 'round', 'projecting'}` |
| `dash_joinstyle` | `{'miter', 'round', 'bevel'}` |
| `dashes` | 浮点顺序(以磅为单位的开/关油墨)或 `(None, None)` |
| `drawstyle` 或 `ds` | `{'default', 'steps', 'steps-pre', 'steps-mid', 'steps-post'}`，默认值: `'default'` |
| `figure` | `Figure` |
| `fillstyle` | `{'full', 'left', 'right', 'bottom', 'top', 'none'}` |
| `gid` | 字符串 |
| `in_layout` | 布尔值 |
| `label` | 文本对象 |
| `linestyle` 或 `ls` | `{'-', '--', '-.', ':', '', (offset, on-off-seq), ...}` |
| `linewidth` 或 `lw` | 浮点数 |
| `marker` | 标记样式 |
| `markeredgecolor` 或 `mec` | 颜色 |
| `markeredgewidth` 或 `mew` | 浮点数 |
| `markerfacecolor` 或 `mfc` | 颜色 |
| `markerfacecoloralt` 或 `mfcalt` | 颜色 |
| `markersize` 或 `ms` | 浮点数 |
| `markevery` | `None 或 int 或 (int, int) 或 slice 或 list[int] 或 float 或 (float, float)` |
| `path_effects` | `AbstractPathEffect` |
| `picker` | `float 或 callable[[Artist, Event], tuple[bool, dict]]` |
| `pickradius` | 浮点数 |
| `rasterized` | `bool 或 None` |
| `sketch_params` | `(scale: float, length: float, randomness: float)` |
| `snap` | `bool 或 None` |
| `solid_capstyle` | `{'butt', 'round', 'projecting'}` |
| `solid_joinstyle` | `{'miter', 'round', 'bevel'}` |
| `transform` | `matplotlib.transforms.Transform` |
| `url` | 字符串 |
| `visible` | 布尔值 |
| `xdata` | 1D 数组 |
| `ydata` | 1D 数组 |
| `zorder` | 浮点数 |

**例 1:**

```py
import matplotlib.pyplot as plt
import numpy as np
import matplotlib.mlab as mlab
import matplotlib.gridspec as gridspec

# set random state for reproducibility
np.random.seed(19695601)

diff = 0.01
ax = np.arange(0, 10, diff)
n = np.random.randn(len(ax))
by = np.exp(-ax / 0.05)

cn = np.convolve(n, by) * diff
cn = cn[:len(ax)]
s = 0.1 * np.sin(2 * np.pi * ax) + cn

plt.subplot(211)
plt.plot(ax, s)
plt.subplot(212)
plt.psd(s, 512, 1 / diff)

plt.show()
```

**输出:**

![spectral density in Python using Matplotlib](img/b051a2bb5ef9d9cf397252950b5a34cd.png)

**例 2:**

```py
import matplotlib.pyplot as plt
import numpy as np
import matplotlib.mlab as mlab
import matplotlib.gridspec as gridspec

# set random value to ensure reproducibility
random_rep = np.random.RandomState(19680801)

frame_per_second = 1000
a = np.linspace(0, 0.3, 301)
b = np.array([2, 8]).reshape(-1, 1)
c = np.array([150, 140]).reshape(-1, 1)
d = (b * np.exp(2j * np.pi * c * a)).sum(axis = 0) + 5 * random_rep.randn(*a.shape)

figure, (a0, a1) = plt.subplots(ncols = 2,
                                constrained_layout = True)

e = np.arange(-50, 30, 10)
f = (e[0], e[-1])
g = np.arange(-500, 550, 200)

a0.psd(d, NFFT = 301,
       Fs = frame_per_second,
       window = mlab.window_none,
       pad_to = 1024,
       scale_by_freq = True)

a0.set_title('Periodo-gram')
a0.set_yticks(e)
a0.set_xticks(g)
a0.grid(True)
a0.set_ylim(f)

a1.psd(d, NFFT = 150,
       Fs = frame_per_second,
       window = mlab.window_none,
       pad_to = 512,
       noverlap = 75,
       scale_by_freq = True)

a1.set_title('Welch')
a1.set_xticks(g)
a1.set_yticks(e)

# overwriting the y-label added by `psd`
a1.set_ylabel('')
a1.grid(True)
a1.set_ylim(f)

plt.show()
```

**输出:**

![spectral density in Python using Matplotlib](img/3899f2c5679ed27c61d3773ee9dc138c.png)