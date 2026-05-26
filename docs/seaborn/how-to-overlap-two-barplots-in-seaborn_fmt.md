# 如何在 Seaborn 中重叠两个 Barplots？

> 原文：[https://www.geeksforgeeks.org/how-to-overlap-two-barplots-in-seaborn/](https://www.geeksforgeeks.org/how-to-overlap-two-barplots-in-seaborn/)

`Seaborn`是一个用 Python 进行统计图形绘制的惊人可视化库。它提供了漂亮的默认样式和颜色调色板，使统计图更有吸引力。它建立在`matplotlib`库的基础上，也紧密集成了来自`pandas`的数据结构。

`barplot`用于使用矩形条表示数据类别。我们可以通过创建子图来重叠`Seaborn`中的两个`barplot`。

## 在`Seaborn`中重叠两个`barplot`所需的步骤：

1.  导入`seaborn`和`matplotlib`库，`seaborn`用于绘图，`matplotlib`用于使用`subplots()`。
2.  正在创建数据框。
3.  在相同的轴上创建两个子图。
4.  展示剧情。

以下是基于上述方法的一些示例：

### 例 1：

```py
# importing all required libraries
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# creating dataframe
df = pd.DataFrame({
    'X': [1, 2, 3],
    'Y': [3, 4, 5],
    'Z': [2, 1, 2]
})

# creating subplots
ax = plt.subplots()

# plotting columns
ax = sns.barplot(x=df["X"], y=df["Y"], color='b')
ax = sns.barplot(x=df["X"], y=df["Z"], color='r')

# renaming the axes
ax.set(xlabel="x-axis", ylabel="y-axis")

# visulaizing illustration
plt.show()
```

**输出：**

![](img/64257f8ceb8823c2f7d710d36e86d000.png)

### 例 2：

```py
#importing all required libraries
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

#creating dataframe
df=pd.DataFrame({
    'X':[i for i in range(10,110,10)],
    'Y':[i for i in range(100,0,-10)],
    'Z':[i for i in range(10,110,10)]
})

#creating subplots
ax=plt.subplots()

#plotting columns
ax=sns.barplot(x=df["X"],y=df["Y"],color = 'lime')
ax=sns.barplot(x=df["X"],y=df["Z"],color = 'green')

#renaming the axes
ax.set(xlabel="x-axis", ylabel="y-axis")

# visulaizing illustration
plt.show()
```

**输出：**

![](img/947e317a373917fd151a20009e6d1579.png)