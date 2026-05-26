# 如何用 Python 将图例放置在 Seaborn 图表外？

> 原文：[https://www.geeksforgeeks.org/how-to-place-legend-outside-the-plot-with-seaborn-in-python/](https://www.geeksforgeeks.org/how-to-place-legend-outside-the-plot-with-seaborn-in-python/)

**Seaborn** 是基于 `matplotlib` 的 Python **数据可视化库**。它提供了一个高级界面，用于绘制吸引人且信息丰富的统计图形。基本上，它帮助我们风格化我们使用 `matplotlib` 制作的基本图表。此外，它还为我们提供了不同的绘图技术来简化我们的**探索性数据分析(EDA)**。有了这些图表，为特定图表提供图例也变得很重要。

在接下来的这篇文章中，我们将看到如何将我们的图例放置在我们的图表上，在本文的后面，我们还将看到如何使用 **Seaborn** 将图例放置在图表之外。

## 导入必要的库

我们将从导入必要的库开始。

```py
import seaborn as sns
import matplotlib.pyplot as plt
```

## 绘制数据

我们将使用 `Seaborn` 不仅绘制数据，而且导入我们的数据集。在这里，我们将使用由 Seaborn 提供的**伽马数据集**。

```py
# set our graph style to whitegrid
sns.set(style="whitegrid")

# load the gammas dataset
ds = sns.load_dataset("gammas")

# use seaborn's lineplot to plot our timeplot
# and BOLD signal columns
sns.lineplot(data=ds, x="timepoint", y="BOLD signal", hue = "ROI")

plt.show()
```

**输出：**

![](img/15161abbf387b7f3495f196d227d34ef.png)

我们可以看到，这用图例绘制了一个漂亮的线图。我们可以看到图例框在图表上。这可能是许多图表中的一个问题，所以我们需要将我们的图例框保留在图表之外。

## 将图例放置在图表外

我们可以通过使用 `matplotlib` 的 `plt.legend()` 函数并提供其必要的参数来做到这一点。

```py
plt.legend(bbox_to_anchor=(1, 1), loc=2)
```