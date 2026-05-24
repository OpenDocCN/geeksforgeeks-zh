# 用 Python 计算汇总标准差

> 原文：[https://www.geeksforgeeks.org/calculate-pooled-standard-deviation-in-python/](https://www.geeksforgeeks.org/calculate-pooled-standard-deviation-in-python/)

我们非常清楚标准差是用来衡量数据集中数字的分布的。较小的标准差表明元素的偏差相对于数据集的平均值非常小或非常小；较大的偏差表明项目相对于它们在数据集中的平均值有显著或较大的分布。

我们可以使用 Python 计算标准差，我们将在这里看到。在 Python 3.x 中，我们有巨大的统计计算库。Python 的 `statistics` 是一个内置的 Python 库，用于描述性统计。如果我们的数据集不是太大，或者如果我们不能简单地依赖于导入其他库，我们可以使用它。

## 合并标准差

集合标准差是两个或更多组的标准差的加权平均值。对单个标准差进行平均，对更大的样本量给予更多的“权重”。

这是**科恩的备选公式**这里供参考：

```
SD_pooled = √(((n1-1)*SD1^2 + (n2-1)*SD2^2)/(n1+n2-2))
```

其中，

*   `SD1` = 组 1 的标准差
*   `SD2` = 第 2 组的标准差
*   `n1` = 第 1 组的样本量
*   `n2` = 第 2 组的样本量

对于同等大小的样本，它简单地变成，

```
SD_pooled = √((SD1^2 + SD2^2)/2)
```

## 计算步骤

1.  导入 `statistics` (针对 python 标准差库)
2.  导入 `math` (计算 `sqrt`)
3.  使用 python 中的 `len` 函数确定样本的长度 (假设 `n1 = len(sample1)`)
4.  计算样品的标准差 (例如。`sample1`，使用 `statistics.stdev(sample1)`)
5.  最后，使用公式计算样本的合并标准差。

```
Pooled standard deviation = √ ( (n1-1)*sample1^2 + (n2-1)*sample2^2 ) / (n1+n2-2)
```

注意：如果样本为空，将出现**统计错误**。

### 步骤 1：让我们用一个例子来尝试一下

*   首先，我们导入所需的模块。
*   那么，假设我们有两个样本，`sample1 = [4, 5, 6]` 和 `sample2 = [10, 12, 14, 16, 18, 20]`。现在，`statistics.stdev(sample1)` 计算它的标准偏差 (基本上 `statistics.stdev()` 函数计算 Python 中值列表的样本标准偏差)。

```python
# import module
import math
import statistics
sample1 = [4, 5, 6]

# Computing sample standard deviation for sample1
SD1 = statistics.stdev(sample1)
print("Standard Deviation for 1st sample = ", SD1)
sample2 = [10, 12, 14, 16, 18, 20]

# Computing sample standard deviation for sample2
SD2 = statistics.stdev(sample2)
print("Standard Deviation for 2nd sample = ", SD2)
```

**输出：**

```
Standard Deviation for 1st sample =  1.0
Standard Deviation for 2nd sample =  3.7416573867739413
```

### 步骤 2：然后，让我们使用 Python 中的 `len` 函数计算样本的长度

```python
import math
import statistics
sample1 = [4, 5, 6]

# Computing sample standard deviation for sample1
SD1 = statistics.stdev(sample1)
sample2 = [10, 12, 14, 16, 18, 20]

# Computing sample standard deviation for sample2
SD2 = statistics.stdev(sample2)

# calculate length of 1st sample
n1 = len(sample1)

# calculate length of 2nd sample
n2 = len(sample2)

print("sample1 : length = ", n1, " | S.D. = ", SD1)
print("sample2 : length = ", n2, " | S.D. = ", SD2)
```

**输出：**

```
sample1 : length =  3  | S.D. =  1.0
sample2 : length =  6  | S.D. =  3.7416573867739413
```

### 步骤 3：最后，我们使用上述公式计算合并标准差

```python
import math
import statistics
sample1 = [4, 5, 6]

# Computing sample standard deviation for sample1
SD1 = statistics.stdev(sample1)
sample2 = [10, 12, 14, 16, 18, 20]

# Computing sample standard deviation for sample2
SD2 = statistics.stdev(sample2)

# calculate length of 1st sample
n1 = len(sample1)

# calculate length of 2nd sample
n2 = len(sample2)

pooled_standard_deviation = math.sqrt(
                      ((n1 - 1)*SD1 * SD1 +
                     (n2-1)*SD2 * SD2) /
                                  (n1 + n2-2))
print("Pooled Standard Deviation = ",
      pooled_standard_deviation)
```

**输出：**

```
Pooled Standard Deviation =  3.2071349029490928
```