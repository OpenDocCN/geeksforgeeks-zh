# 如何在 sklearn–Python 中使用 `datasets.fetch_mldata()`？

> 原文: [https://www.geeksforgeeks.org/how-to-use-datasets-fetch_mldata-in-sklearn-python/](https://www.geeksforgeeks.org/how-to-use-datasets-fetch_mldata-in-sklearn-python/)

`mldata.org` 没有强制的惯例来存储数据或命名数据集中的列。该函数的默认行为适用于下面提到的大多数常见情况:

*   存储在列中的数据值是 `Data`，存储在列中的目标值是 `Label`。
*   第一个列表存储目标，第二列存储数据。
*   数组数据存储为 `features` 和 `samples`，需要转置以匹配 `sklearn` 标准。

获取一个机器学习数据集，如果文件不存在，它会自动从 `mldata.org` 下载。

`sklearn.datasets` 包使用函数直接加载数据集: `sklearn.datasets.fetch_mldata()`

## 语法

`sklearn.datasets.fetch_mldata(dataname, target_name='label', data_name='data', transpose_data=True, data_home=None)`

## 参数

*   `dataname` (**str**)：是 `mldata.org` 上的数据集名称，例如 `'iris'`，`'mnist'`。
*   `target_name` (**可选，默认: 'label'**)：接受包含目标值的列的名称或索引，需要传递默认值 `label`。
*   `data_name` (**可选，默认: 'data'**)：接受包含数据的列的名称或索引，需要传递默认值 `data`。
*   `transpose_data` (**可选，默认值: True**)：传输的默认值是 `True`。如果为 `True`，加载的数据将被转置。
*   `data_home` (**可选，默认: None**)：加载数据集的缓存文件夹。默认情况下，所有 `sklearn` 数据都存储在子文件夹 `~/scikit_learn_data` 中。

## 返回

数据，一个 `Bunch` 对象，其有趣的属性有: `data`（要学习的数据）、`target`（分类标签）、`DESCR`（数据集描述）、`col_names`（数据集列的原始名称）。

## 示例

### 示例 1: 从 mldata 中加载需要转置的 `'iris'` 数据集。

```py
# import fetch_mldata function
from sklearn.datasets.mldata import fetch_mldata

# load data and transpose data
iris = fetch_mldata('iris',
                    transpose_data = False)

# iris data is very large
# so print the dataset shape
# print(iris)
print(iris.data.shape)
```

**输出:**

```py
(4, 150)
```

### 示例 2: 从 mldata 加载 MNIST 数字识别数据集。

```py
# import fetch_mldata function
from sklearn.datasets.mldata import fetch_mldata

# load data 
mnist = fetch_mldata('MNIST original')

# mnist data is very large
# so  print the shape of data
print(mnist.data.shape)
```

**输出:**

```py
(70000, 784)
```

**注:** 此帖根据 Scikit-learn (0.19 版) 发布。