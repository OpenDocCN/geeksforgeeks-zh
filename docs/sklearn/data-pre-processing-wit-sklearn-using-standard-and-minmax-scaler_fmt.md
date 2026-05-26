# 使用标准和最小最大定标器通过 Sklearn 进行数据预处理

> 原文: [https://www.geeksforgeeks.org/data-pre-processing-wit-sklearn-using-standard-and-minmax-scaler/](https://www.geeksforgeeks.org/data-pre-processing-wit-sklearn-using-standard-and-minmax-scaler/)

数据缩放是数值特征的数据预处理步骤。许多机器学习算法，如梯度下降法、KNN 算法、线性和逻辑回归等。需要数据缩放才能产生好的结果。为此定义了各种定标器。本文主要研究标准定标器和最小-最大定标器。这里的任务是讨论它们的含义以及如何使用这个包附带的内置函数来实现它们。

除了支持库函数之外，将用于实现该功能的其他函数有:

*   `fit(data)` 方法用于计算给定特征的平均值和标准偏差，以便进一步用于缩放。
*   `transform(data)` 方法用于使用使用计算的平均值和标准偏差执行缩放。`fit()` 方法。
*   `fit_transform()` 方法同时进行拟合和变换。

## 标准定标器

标准标度有助于获得标准化分布，平均值为零，标准差为 1（单位方差）。它通过从特征中减去平均值，然后将结果除以特征标准差来标准化特征。

标准比例计算如下:

```py
z = (x - u) / s
```

哪里，

*   `z` 是缩放数据。
*   `x` 是要缩放的数据。
*   `u` 是训练样本的平均值
*   `s` 是训练样本的标准差。

Sklearn 预处理支持 `StandardScaler()` 方法，只需 2-3 步即可直接实现。

> **语法:** `class sklearn.preprocessing.StandardScaler(*, copy=True, with_mean=True, with_std=True)`
>
> **参数:**
>
> *   `copy`: 如果为假，则就地缩放。如果为真，将创建副本，而不是就地缩放。
> *   `with_mean`: 如果为真，数据在缩放前居中。
> *   `with_std`: 如果为真，则数据按单位方差缩放。

**进场:**

*   导入模块
*   创建数据
*   计算所需值
*   打印已处理的数据

**示例:**

```py
# import module
from sklearn.preprocessing import StandardScaler

# create data
data = [[11, 2], [3, 7], [0, 10], [11, 8]]

# compute required values
scaler = StandardScaler()
model = scaler.fit(data)
scaled_data = model.transform(data)

# print scaled data
print(scaled_data)
```

**输出:**

> [[ 0.97596444 -1.61155897]
>
>  [-0.66776515  0.08481889]
>
>  [-1.28416374  1.10264561]
>
>  [ 0.97596444  0.42409446]]

## 上下限缩放器

还有另一种数据缩放方式，即使特征的最小值等于零，特征的最大值等于一。最小最大缩放器在给定的范围内缩小数据，通常是 0 到 1。它通过将要素缩放到给定范围来转换数据。它将值缩放到特定的值范围，而不改变原始分布的形状。

最小最大缩放使用以下方法完成:

> `x_std = (x – x.min(axis=0)) / (x.max(axis=0) – x.min(axis=0))`
>
> `x_scaled = x_std * (max – min) + min`

哪里，

*   `min`, `max` = 特征范围
*   `x.min(axis=0)`: 最小特征值
*   `x.max(axis=0)`: 最大特征值

Sklearn 预处理定义了 `MinMaxScaler()` 方法来实现这一点。

> **语法:** `class sklearn.preprocessing.MinMaxScaler(feature_range=(0, 1), *, copy=True, clip=False)`
>
> **参数:**
>
> *   `feature_range`: 缩放数据的期望范围。最小最大缩放器返回的特征的默认范围是 0 到 1。该范围以元组形式提供为 `(min, max)`。
> *   `copy`: 如果为假，则就地缩放。如果为真，将创建副本，而不是就地缩放。
> *   `clip`: 如果为真，缩放后的数据将被裁剪到提供的特征范围内。

**进场:**

*   导入模块
*   创建数据
*   缩放数据
*   打印缩放数据

**示例:**

```py
# import module
from sklearn.preprocessing import MinMaxScaler

# create data
data = [[11, 2], [3, 7], [0, 10], [11, 8]]

# scale features
scaler = MinMaxScaler()
model=scaler.fit(data)
scaled_data=model.transform(data)

# print scaled features
print(scaled_data)
```

**输出:**

> [[1.         0.        ]
>
> [0.27272727 0.625     ]
>
> [0.         1.        ]
>
> [1.         0.75      ]]