# 如何用 Python 中的牛郎星制作抖动数据点的箱线图？

> 原文：[https://www.geeksforgeeks.org/how-to-make-boxplot-with-jittered-data-points-using-altair-in-python/](https://www.geeksforgeeks.org/how-to-make-boxplot-with-jittered-data-points-using-altair-in-python/)

在本文中，我们将确定使用阿尔泰形成带有数据点的箱线图的方法。最新版本的阿尔泰支持制作简单的方块图。然而，当前版本的阿尔泰不支持在方块图的顶部添加抖动的数据点。因为加州理工学院的贾斯汀·博伊斯，我们将使用他的数据可视化实用程序包`altair-catplot`，我们将使用抖动的数据点制作箱线图。

*   [`Niulangxing`](https://www.geeksforgeeks.org/introduction-to-altair-in-python/)：`Niulangxing`是 Python 中的一个统计可视化库。它是声明性的，基于 Vega 和 Vega-Lite 的可视化语法。它正迅速成为人们寻找快速有效方法来可视化数据集的首选。如果您使用过像`matplotlib`这样的命令式可视化库，您将能够正确理解阿尔泰的能力。
*   [`Catplot`](https://seaborn.pydata.org/api.html)：`Catplot`是 Seaborn 的一个相对较新的补充，它简化了涉及分类变量的绘图。在 Seaborn 0.9.0 版本于 2018 年 7 月发布时，旧的`factorplot`被更改为`catplot`，使其更符合`pandas`和`seaborn`的术语。
*   **箱线图：** 我们可以创建以下箱线图。注意，`mark`是一个字符串，它指定了一个箱线图（在未来的阿尔泰中也是如此），而`encoding`是一个被指定为键值对的字典。

## 所需步骤

1.  导入库
2.  导入或创建数据
3.  将`altair_catplot.catplot()`方法与`jitterbox`变换一起使用。
4.  修改不同属性的值以获得更好的可视化效果（可选）。

## 例 1：Python 3

```py
# importing packages
import altair
import altair_catplot
import seaborn

# load data
tip = seaborn.load_dataset('tips')

# draw a plot
altair_catplot.catplot(tip,
                       transform='jitterbox',
                       mark='point',
                       encoding=dict(x=altair.X('time:N', title=None),
                                     y=altair.Y('total_bill:Q', scale=altair.Scale(zero=False)),
                                     color=altair.Color('time:N', legend=None))
                      )
```