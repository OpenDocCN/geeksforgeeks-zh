# Python中的matplotlib.axis.tick.set_path_effects()函数

> 原文：[https://www.geeksforgeeks.org/matplotlib-axis-tick-set_path_effects-function-in-python/](https://www.geeksforgeeks.org/matplotlib-axis-tick-set_path_effects-function-in-python/)

[**Matplotlib**](https://www.geeksforgeeks.org/python-introduction-matplotlib/) 是Python中的一个库，是NumPy库的数值-数学扩展。这是一个神奇的Python可视化库，用于2D数组图，并用于处理更广泛的SciPy堆栈。

## matplotlib.axis.tick.set_path_effects()函数

matplotlib库的轴模块中的 `Tick.set_path_effects()` 函数用于设置路径效果。

> **语法:** `Tick.set_path_effects(self, path_effects)`
>
> **参数:** 该方法接受以下参数。
>
> *   **path_effects:** 此参数为抽象路径效果。
>
> **返回值:** 此方法不返回值。

以下示例说明 `matplotlib.axis.tick.set_path_effects()` 函数在matplotlib.axis中的用法：

### 示例 1

```py
# Implementation of matplotlib function
from matplotlib.axis import Tick
import matplotlib.pyplot as plt
import numpy as np
import matplotlib.patheffects as path_effects

fig, ax = plt.subplots()
t = ax.text(0.02, 0.5,
            'GeeksForGeeks',
            fontsize = 40,
            weight = 1000,
            va ='center')

Tick.set_path_effects(t, [path_effects.PathPatchEffect(offset =(4, -4),
                                         hatch ='xxxx',
                                         facecolor ='lightgreen'),
                    path_effects.PathPatchEffect(edgecolor ='white',
                                         linewidth = 1.1,
                                         facecolor ='yellow')])

fig.suptitle('matplotlib.axis.Tick.set_path_effects() \
function Example', fontweight ="bold")

plt.show()
```

**输出:**

![](img/f234577fba6404bab8d6e711411e6a9d.png)

### 示例 2

```py
# Implementation of matplotlib function
from matplotlib.axis import Tick
import matplotlib.pyplot as plt
import matplotlib.patheffects as PathEffects
import numpy as np

fig, ax1 = plt.subplots()
ax1.imshow([[1, 2], [2, 3]])

txt = ax1.annotate("Fourth Qaud",
                   (1., 1.),
                   (0., 0),
                   arrowprops = dict(arrowstyle ="->",
                                     connectionstyle ="angle3",
                                     lw = 2),
                   size = 20, ha ="center",
                   path_effects =[PathEffects.withStroke(linewidth = 3,
                                                         foreground ="r")])

Tick.set_path_effects(txt.arrow_patch, [
    PathEffects.Stroke(linewidth = 5,
                       foreground ="r"),
    PathEffects.Normal()])

ax1.grid(True, linestyle ="-")

pe = [PathEffects.withStroke(linewidth = 3,
                             foreground ="r")]

for l in ax1.get_xgridlines() + ax1.get_ygridlines():
    Tick.set_path_effects(l, pe)

fig.suptitle('matplotlib.axis.Tick.set_path_effects() \
function Example', fontweight ="bold")

plt.show()
```

**输出:**

![](img/cacd0adf9a036c77d2ba232ac45d756e.png)