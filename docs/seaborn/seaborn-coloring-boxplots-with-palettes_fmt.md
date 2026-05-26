# 用Seaborn调色板为箱型图着色

> 原文: [https://www.geeksforgeeks.org/seaborn-coloring-boxplots-with-palettes/](https://www.geeksforgeeks.org/seaborn-coloring-boxplots-with-palettes/)

在数据可视化中添加合适的颜色集会使其更令人印象深刻，可读性更强。`seaborn`调色板使您可以轻松地在可视化中使用颜色。在这篇文章中，我们将看到如何使用`seaborn`调色板为`箱型图`上色。还将学习`seaborn`调色板的用法，它也可以应用于其他地块。

## 分步方法

### 第 1 步：加载所需的 Python 包和库

```py
# import libraries
import seaborn as sns
import matplotlib.pyplot as plt
```

### 第 2 步：加载数据集以生成箱线图

```py
# loading dataset
ds = sns.load_dataset('iris')
```

### 第 3 步：使用 `boxplot()` 方法生成箱线图

```py
# create boxplot object
ax = sns.boxplot(data=tips, orient="h")
```

### 第 4 步：使用调色板参数

`seaborn`的`boxplot()`函数有`palette`参数。在这个例子中，我们设置了`palette="Set1"`，它使用定性调色板`Set1`为`boxplot`中的盒子上色。因此，在`boxplot`方法中增加`palette`参数。

```py
# use palette method
ax = sns.boxplot(data=ds, orient="h", palette="Set1")
```

## 完整代码示例

以下是基于上述方法的完整程序：

```py
# import libraries
import seaborn as sns
import matplotlib.pyplot as plt

# load dataset
ds = sns.load_dataset("tips")

plt.figure(figsize=(8, 6))

# use palette method
ax = sns.boxplot(data=ds, orient="h", palette="Set1")
```

### 输出

![](img/0bf097e4bb055f374af93f5216768ce4.png)

用Seaborn调色板给箱型图着色