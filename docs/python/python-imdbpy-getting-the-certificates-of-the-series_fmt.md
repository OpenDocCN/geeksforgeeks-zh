# Python IMDbPY–获取系列证书

> 原文：`https://www.geeksforgeeks.org/python-imdbpy-getting-the-certificates-of-the-series/`

在这篇文章中，我们将看到我们如何才能获得系列证书，证书基本上是给每个系列的证书，它讲述了电影的性质，如年龄限制证书每个证书因国家而异。

> 为了做到这一点，我们必须做到以下几点–
> 1. 借助 `get_movie` 方法获取系列详情。
> 2. 由于这个对象将作为字典，因此我们必须过滤对象。
> 3. 借助 `data` 方法获取对象的主要数据。
> 4. 从字典中获取证书详细信息。

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

# getting certificates of the series
certificate = series.data['certificates']

# printing the object i.e name
print(series)

# print the certificate
print(certificate)
```

**输出：**

```py
Money Heist
['Argentina:16', 'Australia:MA15+::(Netflix self-rating)', 'Brazil:16', 'Canada:TV-MA::(self-applied)', 'France:16', 'Germany:16', 'India:16+::(self-applied)', 'Italy:VM14', 'Japan:R18+::(self-applied)', 'Mexico:TV-MA::(self-applied)', 'Netherlands:12::(season 1)', 'Netherlands:16::(seasons 2-4)', 'Singapore:M18', 'South Korea:18', 'Spain:16', 'Turkey:15+', 'United Kingdom:15', 'United Kingdom:18::(season 4)', 'United States:TV-MA', 'Vietnam:C18']
```

另一个例子：

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "6077448"

# getting information
series = ia.get_movie(code)

# getting certificates of the series
certificate = series.data['certificates']

# printing the object i.e name
print(series)

# print the certificate
print(certificate)
```

**输出：**

```py
Sacred Games
['Argentina:16', 'Australia:MA15+', 'Brazil:18::(self-applied)', 'France:16', 'Germany:16', 'India:A', 'India:UA::(trailer)', 'Italy:VM18', 'Netherlands:16', 'Norway:16::(Netflix self-rating)', 'Singapore:R21', 'South Korea:18', 'Spain:16', 'United Kingdom:18', 'United States:TV-MA::(Netflix)']
```