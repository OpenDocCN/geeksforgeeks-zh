# Python IMDbPY–获得系列投票数

## 介绍

> 原文: [https://www.geeksforgeeks.org/python-imdbpy-getting-number-of-votes-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-number-of-votes-of-the-series/)

在这篇文章中，我们将看到如何获得该系列的投票数，投票数基本上是投票给该系列并对该系列给出评级的人数，评级是每次投票的平均值。

> 为了做到这一点，我们必须做到以下几点–
> 1. 借助 `get_movie` 方法获取系列详情。
> 2. 由于这个对象将作为字典，因此我们必须过滤对象。
> 3. 借助 `data` 方法获取对象的主要数据，返回字典。
> 4. 从字典中获取投票详情。

下面是实现：

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6077448"

# getting information
series = ia.get_movie(code)

# getting votes of the series
votes = series.data['votes']

# printing the object i.e name
print(series)

# print the votes
print(votes)
```

**输出:**

```py
Sacred Games
```

## 示例1

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6468322"

# getting information
series = ia.get_movie(code)

# getting votes of the series
votes = series.data['votes']

# printing the object i.e name
print(series)

# print the votes
print(votes)
```

**输出:**

```py
Money Heist
```