# 在Python Pandas中实现类似Excel的COUNTIFS功能

> 原文：[https://www.geeksforgeeks.org/performing-excel-like-countifs-in-python-pandas/](https://www.geeksforgeeks.org/performing-excel-like-countifs-in-python-pandas/)

在这篇文章中，我们在Pandas中实现了一个类似Excel的COUNTIFS功能。在Excel中，数据以表格形式存在，因此我们可以执行许多算术运算，例如对值求和、计算平均值以及计数等，这些操作通过在指定列上设置条件来完成。同样，我们也可以在Python中对Pandas DataFrame执行所有这些操作，因为DataFrame同样以表格格式维护数据。

## COUNTIFS功能简介

这是一种通过指定一个或多个条件（类似于在在线购物应用程序中应用过滤器）来查找行数以获得所需结果的操作。有一些类似的方法，如`count()`，以及`sum()`、`mean()`等，用于相应地求出数据的总和和平均值。

### 示例1：统计特定品牌和类型的服装数量

```python
# import necessary packages
import pandas as pd

# create a dataframe
costumes = pd.DataFrame({'Brand': ['Twills', 'Wrogn',
                                   'Twills', 'Trigger',
                                   'Twills', 'Wrogn', ],
                         'Costume_Type': ['Shirt', 'Shirt',
                                          'Shirt', 'Jeans',
                                          'T-Shirt', 'Jeans'],
                         'price': [1699, 1999, 1569,
                                   2000, 569, 2400]})

# DataFrame
print(costumes)

# find count of Twills Shirts
twills_Shirt_Count = costumes.query('Brand=="Twills" \
& Costume_Type=="Shirt"')['Costume_Type'].count()

print('Number of Twills Shirts-', end="")
print(twills_Shirt_Count)
```

**输出：**

```python
Number of Twills Shirts-2
```

![](img/d3eac8096d315d4fe756a8d5caadb102.png)

**解释：** 因为我们有3件Twills品牌的物品，但是在这3件物品中，有2件衣服的类型是衬衫，所以结果返回了2。

### 示例2：统计所有品牌的衬衫数量

这里我们使用上面相同的数据框，但是不查找Twills品牌衬衫的数量，而是查找任何品牌的衬衫数量。

```python
# import necessary packages
import pandas as pd

# create a dataframe
costumes = pd.DataFrame({'Brand': ['Twills', 'Wrogn', 
                                   'Twills', 'Trigger',
                                   'Twills', 'Wrogn', ],
                         'Costume_Type': ['Shirt', 'Shirt',
                                          'Shirt', 'Jeans', 
                                          'T-Shirt', 'Jeans'],
                         'price': [1699, 1999, 1569, 
                                   2000, 569, 2400]})

# DataFrame
print(costumes)

# find count of Twills Shirts
Shirt_Count = costumes.query('Costume_Type=="Shirt"')['Costume_Type'].count()

print('\nNumber of Shirts-', end="")
print(Shirt_Count)
```

**输出：**

![](img/231a368d2092b56a59df13e26a284bef.png)

### 示例3：统计价格低于或等于2000的牛仔裤数量

使用上面的服装数据框找到价格小于等于2000的牛仔裤的数量。

```python
# import necessary packages
import pandas as pd

# create a dataframe
costumes = pd.DataFrame({'Brand': ['Twills', 'Wrogn',
                                   'Twills', 'Trigger', 
                                   'Twills', 'Wrogn', ],
                         'Costume_Type': ['Shirt', 'Shirt', 
                                          'Shirt', 'Jeans', 
                                          'T-Shirt', 'Jeans'],
                         'price': [1699, 1999, 1569,
                                   2000, 569, 2400]})

# DataFrame
print(costumes)

# find count of Twills Shirts
Jeans_Count = costumes.query('Costume_Type=="Jeans" & price<=2000')[
    'Costume_Type'].count()

print('\nNumber of Jeans below or equals to Rs.2000-', end=" ")
print(Jeans_Count)
```

**输出：**

![](img/b25a9696d480f8f796cf45cb6e2b38fc.png)