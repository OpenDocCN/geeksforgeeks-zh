# 使用 Python 中的 sklearn 计算完整性分数

> 原文：[https://www.geeksforgeeks.org/calculating-the-completeness-score-using-sklearn-in-python/](https://www.geeksforgeeks.org/calculating-the-completeness-score-using-sklearn-in-python/)

一个完全完整的集群是指每个集群都有指向相似类集群的信息。完备性描述了聚类算法对这种（完备性分数）完善性的接近程度。

这个度量独立于标签的直接值。聚类标签值的排列不会以任何方式改变分值。

## `sklearn.metrics.completeness_score()`

> **语法：** `sklearn.metrics.completeness_score(labels_true, labels_pred)`
>
> **参数：**
>
> *   `labels_true`：`<int array, shape = [n_samples]>`：它接受地面真值类标签作为参考。
> *   `labels_pred`：`<array-like of shape (n_samples,)>`：它接受要评估的聚类标签。
>
> **返回：** 0.0-1.0 之间的完整性分数。1.0 代表完美的完整性标签。

用 `label_pred` 切换 `label_true` 将返回同质性分数。

### 例 1

```py
# Importing the modules
import pandas as pd
from sklearn import datasets
from sklearn.cluster import KMeans
from sklearn.metrics import completeness_score

# Loading the data
digits = datasets.load_digits()

# Separating the dependent and independent variables
Y = digits.target
X = digits.data

# Building the clustering model
kmeans = KMeans(n_clusters = 2)

# Training the clustering model
kmeans.fit(X)

# Storing the predicted Clustering labels
labels = kmeans.predict(X)

# Evaluating the performance
print(completeness_score(Y, labels))
```

**输出：**

```py
0.8471148027985769
```

### 示例 2：完全完整性

```py
# Importing the module
from sklearn.metrics.cluster import completeness_score

# Evaluating the score
Cscore = completeness_score([0, 1, 0, 1],
                            [1, 0, 1, 0])
print(Cscore)
```