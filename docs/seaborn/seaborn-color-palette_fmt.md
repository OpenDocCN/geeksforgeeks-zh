# seaborn–color palette

> 原文: [https://www.geeksforgeeks.org/seaborn-color-palette/](https://www.geeksforgeeks.org/seaborn-color-palette/)

在本文中，我们将看到 `seaborn.color_palette()`，可用于为剧情着色。使用调色板我们可以生成具有不同[颜色](https://seaborn.pydata.org/generated/seaborn.color_palette.html#seaborn.color_palette)的点。在下面这个例子中，我们可以看到调色板可以负责生成不同的颜色映射值。

> **语法:** `seaborn.color_palette(*palette=None*, *n_colors=None*, *desat=None*)`
>
> **参数:**
>
> - **palette:** 调色板名称或无返回当前调色板。
> - **n_colors:** 调色板中的颜色数量。
> - **desat:** 比例去饱和每种颜色。
>
> **返回:** RGB 元组或 `matplotlib.colors.Colormap` 的列表

我们将对使用 `color_palette()` 的不同方式进行分类：

- 定性的
- 连续的
- 分歧的

## 定性

当变量本质上是分类的，分配给每个组的颜色需要不同时，使用定性调色板。如图所示，图中的定性调色板为变量的每个可能值分配一种颜色。

![](img/dffecfbda11ed92e60519c19d3ac640b.png)

### 示例

```py
from matplotlib import pyplot as plt
import seaborn as sns
current_palette = sns.color_palette()
sns.palplot(current_palette)
plt.show()
```

**输出:**

![](img/69404c9caefef1b3d94e667e7ccaaa33.png)

## 连续的

连续调色板的颜色从浅到深依次移动。当分配给被着色的变量是数字或具有固有的有序值时，可以用如图所示的顺序调色板来描述它。

![](img/b3ef95b8a740d6312ddd430db74ef686.png)

### 示例

```py
from matplotlib import pyplot as plt
import seaborn as sns
current_palette = sns.color_palette()
sns.palplot(sns.color_palette("Greys"))
plt.show()
```

**输出:**

![](img/c5d1ab14f939548c1014905bfb6c282a.png)

## 分歧的

当我们处理像正负值（低值和高值）这样的混合值时，发散调色板是可视化的最佳选择。

![](img/0957267bc8bc8ce31711371aab6191d4.png)

### 示例

```py
from matplotlib import pyplot as plt
import seaborn as sns
current_palette = sns.color_palette()
sns.palplot(sns.color_palette("terrain_r", 7))
plt.show()
```

**输出:**

![](img/6c6268e9d831a6ef8da98f7efdfaccf8.png)

## 用一些例子来理解一下

### 例 1

在这个例子中，我们使用了 `sns.color_palette()` 来构建一个颜色图，并且使用了 `sns.palplot()` 来显示颜色图中具有“deep”属性的颜色。

```py
# import module
import pandas as pd
import seaborn as sns

sns.palplot(sns.color_palette("deep", 10))
```

**输出:**

![](img/da627276f4eb6727e2521985d666592c.png)

**调色板的可能值为:**

> 'Accent', 'Accent_r', 'Blues', 'Blues_r', 'BrBG', 'BrBG_r', 'BuGn', 'BuGn_r', 'BuPu', 'BuPu_r', 'CMRmap', 'CMRmap_r', 'Dark2', 'Dark2_r', 'GnBu', 'GnBu_r', 'Greens', 'Greens_r', 'Greys', 'Greys_r', 'OrRd', 'OrRd_r', 'Oranges', 'Oranges_r', 'PRGn', 'PRGn_r', 'Paired', 'Paired_r', 'Pastel1', 'Pastel1_r', 'Pastel2', 'Pastel2_r', 'PiYG', 'PiYG_r', 'PuBu', 'PuBuGn', 'PuBuGn_r', 'PuBu_r', 'PuOr', 'PuOr_r', 'PuRd', 'PuRd_r', 'Purples', 'Purples_r', 'RdBu', 'RdBu_r', 'RdGy', 'RdGy_r', 'RdPu', 'RdPu_r', 'RdYlBu', 'RdYlBu_r', 'RdYlGn', 'RdYlGn_r', 'Reds', 'Reds_r', 'Set1', 'Set1_r', 'Set2', 'Set2_r', 'Set3', 'Set3_r', 'Spectral', 'Spectral_r', 'Wistia', 'Wistia_r', 'YlGn', 'YlGnBu', 'YlGnBu_r', 'YlGn_r', 'YlOrBr', 'YlOrBr_r', 'YlOrRd', 'YlOrRd_r', 'afmhot', 'afmhot_r', 'autumn', 'autumn_r', 'binary', 'binary_r', 'bone', 'bone_r', 'brg', 'brg_r', 'bwr', 'bwr_r', 'cividis', 'cividis_r', 'cool', 'cool_r', 'coolwarm', 'coolwarm_r', 'copper', 'copper_r', 'cubehelix', 'cubehelix_r', 'flag', 'flag_r', 'gist_earth', 'gist_earth_r', 'gist_gray', 'gist_gray_r', 'gist_heat', 'gist_heat_r', 'gist_ncar', 'gist_ncar_r', 'gist_rainbow', 'gist_rainbow_r', 'gist_stern', 'gist_stern_r', 'gist_yarg', 'gist_yarg_r', 'gnuplot', 'gnuplot2', 'gnuplot2_r', 'gnuplot_r', 'gray', 'gray_r', 'hot', 'hot_r', 'hsv', 'hsv_r', 'icefire', 'icefire_r', 'inferno', 'inferno_r', 'jet', 'jet_r', 'magma', 'magma_r', 'mako', 'mako_r', 'nipy_spectral', 'nipy_spectral_r', 'ocean', 'ocean_r', 'pink', 'pink_r', 'plasma', 'plasma_r', 'prism', 'prism_r', 'rainbow', 'rainbow_r', 'rocket', 'rocket_r', 'seismic', 'seismic_r', 'spring', 'spring_r', 'summer', 'summer_r', 'tab10', 'tab10_r', 'tab20', 'tab20_r', 'tab20b', 'tab20b_r', 'tab20c', 'tab20c_r', 'terrain', 'terrain_r', 'twilight', 'twilight_r', 'twilight_shifted', 'twilight_shifted_r', 'viridis', 'viridis_r', 'winter', 'winter_r'

### 例 2

在本例中，我们使用了 `sns.color_palette()` 来构建一个颜色映射，并使用 `sns.palplot()` 来显示颜色映射中具有“muted”属性的颜色。

```py
import pandas as pd
import seaborn as sns

sns.palplot(sns.color_palette("muted", 10))
```

**输出:**

![](img/ec82d1cbb57230b3e908a9af27eb14c4.png)

### 例 3

在这个例子中，我们使用了 `sns.color_palette()` 来构建一个颜色图，并且使用了 `sns.palplot()` 来显示颜色图中具有“bright”属性的颜色。

```py
import pandas as pd
import seaborn as sns

sns.palplot(sns.color_palette("bright", 10))
```

**输出:**

![](img/d240858e101081765ef14f67b96a9946.png)

### 例 4

在这个例子中，我们使用了 `sns.color_palette()` 来构建一个颜色图，并且使用了 `sns.palplot()` 来显示颜色图中具有“dark”属性的颜色。

```py
import pandas as pd
import seaborn as sns

sns.palplot(sns.color_palette("dark", 10))
```

**输出:**

![](img/c81bc9b552ac6aab59d47984a6ea4771.png)

### 例 5

在本例中，我们使用了 `sns.color_palette()` 来构建一个颜色映射，并使用了 `sns.palplot()` 来显示带有“BuGn_r”属性的颜色映射中存在的颜色。

```py
import pandas as pd
import seaborn as sns

sns.palplot(sns.color_palette("BuGn_r", 10))
```

**输出:**

![](img/25ee501d8a73d72e47e786db19358a75.png)

### 例 6

在本例中，创建一个自己的调色板，并将其设置为当前调色板。

```py
import pandas as pd
import seaborn as sns

color = ["green", "White", "Red", "Yellow", "Green", "Grey"]
sns.set_palette(color)
sns.palplot(sns.color_palette())
```

**输出:**

![](img/7c6ea71d2aac3680bb723522dea6cce8.png)