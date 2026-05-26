# 如何用Python制作简单的刻面图？

> 原文：[https://www.geeksforgeeks.org/how-to-make-simple-facet-plots-with-seaborn-catplot-in-python/](https://www.geeksforgeeks.org/how-to-make-simple-facet-plots-with-seaborn-catplot-in-python/)

`Seaborn`是一个用Python绘制统计图形的惊人可视化库。它提供了漂亮的默认样式和调色板，使统计图更有吸引力。它建立在`matplotlib`库的基础上，还紧密集成了来自`pandas`的数据结构。
Seaborn旨在将可视化作为探索和理解数据的核心部分。它提供了面向数据集的API，这样我们就可以在不同的可视化表示之间切换，为数据集提供相同的变量，从而更好地理解数据集。

**分面图**，其中一个基于分类变量对数据进行子集化，并制作一系列具有相同比例的相似图。

我们可以通过多种方式在Python中制作刻面图。在这篇文章中，我们将看到一个使用`Seaborn`的`catplot()`方法制作简单小平面图的例子。当有一个数字变量和一个相应的分类变量时，它主要用于可视化。

## 所需步骤

1.  导入库。
2.  导入或创建数据。
3.  将`catplot()`方法与`小平面曲线`一起使用。
4.  使用其他参数以获得更好的可视化效果。

## 使用的数据集

下例中使用的数据集是[https://www.kaggle.com/ranjeetjain3/seaborn-tips-dataset](https://www.kaggle.com/ranjeetjain3/seaborn-tips-dataset)

## 以下是一些使用 Seaborn 模块描绘小平面图的示例

### 例 1

```python
# importing packages
import seaborn

# load data
tip = seaborn.load_dataset('tips')

# create catplot facetplot object
seaborn_facetgrid_object = seaborn.catplot(
    x='sex',
    y='tip',
    data=tip
)
# show plot
seaborn_facetgrid_object
```

**输出：**

![](img/642e5bf3c6db2a6ffb8b0cb4b35d0ab4.png)

### 例 2

```python
# importing packages
import seaborn

# load data
tip = seaborn.load_dataset('tips')

# create catplot facetplot object
seaborn_facetgrid_object = seaborn.catplot(
    x='sex',
    y='tip',
    kind='box',
    data=tip
)
# show plot
seaborn_facetgrid_object
```

**输出：**

![](img/f6962065fea828ddc420f48779a6af45.png)

### 例 3

```python
# importing packages
import seaborn

# load data
tip = seaborn.load_dataset('tips')

# create catplot facetplot object
seaborn_facetgrid_object = seaborn.catplot(
    x='sex',
    y='tip',
    col='time',
    kind='box',
    data=tip
)
# show plot
seaborn_facetgrid_object
```

**输出：**

![](img/ad848041445384a0710035415819696d.png)

### 例 4

```python
# importing packages
import seaborn

# load data
tip = seaborn.load_dataset('tips')

# create catplot facetplot object
seaborn_facetgrid_object = seaborn.catplot(
    x='sex',
    y='tip',
    row='time',
    col='day',
    aspect=0.9,
    dodge=False,
    kind='box',
    data=tip
)
# show plot
seaborn_facetgrid_object
```

**输出：**

![](img/08ae8cde86a11662d603c510e1422983.png)