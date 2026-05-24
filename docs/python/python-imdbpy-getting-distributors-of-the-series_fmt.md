# Python IMDbPY–获得该系列的分销商

> 原文: [https://www.geeksforgeeks.org/python-imdbpy-getting-distributors-of-the-series/](https://www.geeksforgeeks.org/python-imdbpy-getting-distributors-of-the-series/)

在本文中，我们将了解如何获得该系列的分销商。分销商基本上是那些电视转播该系列的公司，例如网飞和亚马逊 prime 等。

> 为了做到这一点，我们必须做到以下几点–
> 1. 借助 `get_movie` 方法获取系列详情。
> 2. 由于这个对象将作为字典，因此我们必须过滤对象。
> 3. 借助返回字典的 `data` 方法获取对象的主要数据。
> 4. 从字典里找经销商。

下面是实现：

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6468322"

# getting information
series = ia.get_movie(code)

# getting distributors companies of the series
distributors = series.data['distributors']

# printing the object i.e name
print(series)

# print the distributors
print(distributors)
```

输出:

```py
Money Heist
[Company id:0062576[http] name:_Antena 3 Televisión_, Company id:0144901[http] name:_Netflix_]
```

另一个例子：

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6473300"

# getting information
series = ia.get_movie(code)

# getting distributors companies of the series
distributors = series.data['distributors']

# printing the object i.e name
print(series)

# print the distributors
print(distributors)
```

输出:

```py
Mirzapur
[Company id:0700396[http] name:_Amazon Prime Video_]
```