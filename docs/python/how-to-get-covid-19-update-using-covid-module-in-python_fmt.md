# 如何使用 Python 中的 COVID 模块获取 COVID-19 更新？

> 原文：[https://www.geeksforgeeks.org/how-to-get-covid-19-update-using-covid-module-in-python/](https://www.geeksforgeeks.org/how-to-get-covid-19-update-using-covid-module-in-python/)

一个新的 Python 库提供新冠肺炎相关的信息（按国家），它显示在那个特定的国家发现了多少确诊的、活跃的、死亡的病例。

## 需求

你有一个名为 `COVID` 的 Python 包，`python >= 3.6`。

## 安装

```py
pip install covid
```

## 依赖关系

*   `requests`
*   `requests`

## 示例

```py
from covid import Covid

covid = Covid()
india = covid.get_status_by_country_name("india")

data ={
    key:india[key]
    for key in india.keys() and {'confirmed', 
                                 'active',
                                 'deaths',
                                 'recovered'}
}

print(data)
```

## 输出

> { 'confirmed':119419, 'active':66863, 'recovered':48957, 'deaths':3599}

让我们看看模块的基本功能。

### List Countries and their Id’s

This comes in need when you need to know the names of countries while using `get_status_by_country_name`, eg to use ‘America’ or ‘United States of America’ or ‘US’.

```py
from covid import Covid

covid = Covid()
countries = covid.list_countries()

print(countries)
```

**输出：**

> [{'id': '18', 'name': 'US'}, {'id': '14', 'name': 'Russia'}, {'id': '22', 'name': 'Brazil'}, {'id': '17', 'name': 'UK'}, {'id': '19', 'name': 'Spain'}, {'id': '11', 'name': 'Italy'}, {'id': '7', 'name': 'France'}, {'id': '8', 'name': 'Germany'}, {'id': '11', ...}]

**注意：** 列表太长，以上输出只是列表的一部分。

### Get Data

To get COVID-19 related information.

```py
from covid import Covid

covid = Covid()
print(covid.get_data())
```

**输出：**

> [{'id': '18', 'country': 'US', 'confirmed': 1577758, 'active': 1181132, 'deaths': 94729, 'recovered': 298418, 'latitude': 40.0, 'longitude': -100.0, 'last_update': 1590143562000}, {'id': '14', 'country': 'Russia', 'confirmed': 326448, 'active': 2233374, 'deaths': 3249, 'recovered': ...}]

**注意：** 列表太长，以上输出只是列表的一部分。

### Get Status By Country ID

To get COVID-19 related information by Country Id.

```py
from covid import Covid

covid = Covid()
cases = covid.get_status_by_country_id(18)

print(cases)
```

**输出：**

> {'id': '18', 'country': 'US', 'confirmed': 1541110, 'active': 1154535, 'deaths': 92712, 'recovered': 289392, 'latitude': 40.0, 'longitude': -100.0, 'last_update': 1590003166000}

### Get Status By Country Name

```py
from covid import Covid

covid = Covid()
italy_cases = covid.get_status_by_country_name("italy")

print(italy_cases)
```

**输出：**

> {'id': '11', 'country': 'Italy', 'confirmed': 227364, 'active': 62752, 'deaths': 32330, 'recovered': 132282, 'latitude': 41.8719, 'longitude': 12.5674, 'last_update': 1590003166000}

### Get Total Confirmed cases, Active cases, Recovered cases and Deaths

```py
from covid import Covid

covid = Covid()

confirmed = covid.get_total_confirmed_cases()
print('Confirmed :', end =" ")
print(confirmed)

active = covid.get_total_active_cases()
print("Active:", end =" ")
print(active)

recovered = covid.get_total_recovered()
print('Recovered:', end =" ")
print(recovered)

deaths = covid.get_total_deaths()
print('Deaths:', end =" ")
print(deaths)
```

**输出：**

```py
Confirmed : 4955312
Active: 2750033
Recovered: 1874998
Deaths: 325810
```