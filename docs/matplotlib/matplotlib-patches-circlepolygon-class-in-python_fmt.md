# Python中的matplotlib.patches.CirclePolygon类

> 原文：[https://www.geeksforgeeks.org/matplotlib-patches-circlepolygon-class-in-python/](https://www.geeksforgeeks.org/matplotlib-patches-circlepolygon-class-in-python/)

[Matplotlib](https://www.geeksforgeeks.org/python-matplotlib-an-overview/) 是Python中一个惊人的可视化库，用于数组的2D图。Matplotlib是一个多平台数据可视化库，构建在NumPy数组上，旨在与更广泛的SciPy堆栈一起工作。

## matplotlib.patches.CirclePolygon

`matplotlib.patches.CirclePolygon`类用于圆形面片的多边形近似。用于在`xy = (x, y)`处做一个半径已经提供的圆。有分辨率边的正多边形用这个圆来近似。

> `语法:` `class matplotlib.patches.CirclePolygon(xy, radius=5, resolution=20, **kwargs)`
>
> `参数:`
>
> *   `xy:` 待画圆的原点坐标。
> *   `radius:` 可选参数，用于设置圆的半径。默认为5个单位。
> *   `resolution:` 顾名思义是用来设置图像分辨率的。它是可选的，默认为20。

下表提供了可选的有效kwargs

| 财产 | 描述 |
| --- | --- |
| agg_filter | 接受(m，n，3)浮点数组和返回(m，n，3)数组的dpi值的筛选函数 |
| alpha | 浮动或无 |
| animated | 弯曲件 |
| antialiased or aa | 未知的 |
| capstyle | { '对接'，'圆形'，'突出' } |
| clip_box | Bbox |
| clip_on | 弯曲件 |
| clip_path | [(路径，转换)|补丁|无] |
| color | rgba元组的颜色或序列 |
| contains | 请求即付的 |
| edgecolor or ec or edgecolors | 颜色或无或“自动” |
| facecolor or fc or facecolors | 颜色或无 |
| figure | 数字 |
| fill | 弯曲件 |
| gid | 潜艇用热中子反应堆（submarine thermal reactor的缩写） |
| hatch | {'/'，' \ '，' | '，'-'，'+'，' x '，' O '，' O '，' ', '*'} |
| in_layout | 弯曲件 |
| joinstyle | { '斜接'，'圆形'，'斜角' } |
| linestyle | {'-', '–', '-.'，':'，"，(偏移量，开-关-序列)，…} |
| linewidth | 浮动或无 |
| path_effects | 抽象路径效应 |
| picker | 无、布尔、浮点或可调用 |
| path_effects | 抽象路径效应 |
| picker | 浮动或可调用[[艺术家，事件]，元组[布尔，字典]] |
| rasterized | 布尔或无 |
| sketch_params | (比例:浮动，长度:浮动，随机性:浮动) |
| snap | 布尔或无 |
| transform | matplotlib.transforms.transform |
| url | 潜艇用热中子反应堆（submarine thermal reactor的缩写） |
| visible | 弯曲件 |
| zorder | 漂浮物 |

**例1:**

```py
import matplotlib.pyplot as plt
from matplotlib.patches import CirclePolygon

circle = CirclePolygon((0, 0), 
                       radius = 0.75,
                       fc = 'y')

plt.gca().add_patch(circle)

verts = circle.get_path().vertices
trans = circle.get_patch_transform()
points = trans.transform(verts)

plt.plot(points[:, 0], points[:, 1])
plt.axis('scaled')

plt.show()
```

**输出:**
![](img/4d7134590f7da3035a0fef5973ec22ac.png)

**例2:**

```py
import numpy as np
import matplotlib
from matplotlib.patches import Circle, Wedge, Polygon, Ellipse
from matplotlib.collections import PatchCollection
import matplotlib.pyplot as plt
import matplotlib.patches as matpatches

fig, ax = plt.subplots(figsize =(8, 8))
patches = []

circle = Circle((2, 2), 2)
patches.append(circle)

polygon = matpatches.PathPatch(patches[0].get_path())
patches.append(polygon)

colors = 2 * np.random.rand(len(patches))
p = PatchCollection(patches, 
                    cmap = matplotlib.cm.jet,
                    alpha = 0.4)

p.set_array(np.array(colors))
ax.add_collection(p)

plt.axis([-10, 10, -10, 10])

plt.show()
```

**输出:**
![](img/7c4e46edac81ffb6c78751a9766472e3.png)