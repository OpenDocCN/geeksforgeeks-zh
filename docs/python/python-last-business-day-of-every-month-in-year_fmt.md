# Python–一年中每个月的最后一个工作日

> 原文: [https://www.geeksforgeeks.org/python-last-business-day-of-every-month-in-year/](https://www.geeksforgeeks.org/python-last-business-day-of-every-month-in-year/)

给定一年和一个工作日，任务是编写一个 Python 程序来提取对应于工作日的每个月的日期。

> **输入:** `year= 1997`，`week= 5`
> 
> **产量:** `['25/1/1997', '22/2/1997', '29/3/1997', '26/4/1997', '31/5/1997', '28/6/1997', '26/7/1997', '30/8/1997', '27/9/1997', '25/10/1997']`
> 
> **说明:** `5` 是周五。1997 年 1 月的最后一个工作日，也就是星期五是 25 日。
> 
> **输入:** `year= 1996`，`week= 4`
> 
> **产量:** `['26/1/1996', '23/2/1996', '29/3/1996', '26/4/1996', '31/5/1996', '28/6/1996', '26/7/1996', '30/8/1996', '27/9/1996', '25/10/1996']`
> 
> **说明:** `4` 是周四。1997 年 1 月的最后一个工作日，也就是星期四，是 26 日。

## 方法#1: 使用循环 + `max()` + `calendar.monthcalendar`

在本例中，我们使用 `monthcalendar()` 从[日历库](https://www.geeksforgeeks.org/python-calendar-module/)中执行获取每个月日历的任务。提取每个工作日的日期，它的最大值，即整个月的最大值，是最后一个工作日，因此被提取。

### Python 3

```py
# Python3 code to demonstrate working of
# Last weekday of every month in year
# Using loop + max() + calendar.monthcalendar
import calendar

# initializing year
year = 1997

# printing Year
print("The original year : " + str(year))

# initializing weekday 
weekdy = 5

# iterating for all months
res = []
for month in range(1, 13):

    # max gets last friday of each month of 1997
    res.append(str(max(week[weekdy] 
                       for week in calendar.monthcalendar(year, month))) +
               "/" + str(month)+ "/" + str(year))

# printing 
print("Last weekdays of year : " + str(res))
```

**输出:**

> 最初年份: 1997 年
> 
> 一年中的最后几个工作日: `['1997年1月25日', '1997年2月22日', '1997年3月29日', '1997年4月26日', '1997年5月31日', '1997年6月28日', '1997年7月26日', '1997年8月30日', '1997年9月27日', '1997年10月25日']`

## 方法二: 使用 `列表理解`

类似于上面的方法，唯一的区别是紧凑解决方案使用列表理解。

### Python 3

```py
# Python3 code to demonstrate working of
# Last weekday of every month in year
# Using list comprehension
import calendar

# initializing year
year = 1997

# printing Year
print("The original year : " + str(year))

# initializing weekday 
weekdy = 5

# list comprehension for shorthand
res = [str(max(week[weekdy]
               for week in calendar.monthcalendar(year, month))) + 
       "/" + str(month)+ "/" + str(year) for month in range(1, 13)]

# printing 
print("Last weekdays of year : " + str(res))
```

**输出:**

> 最初年份: 1997 年
> 
> 一年中的最后几个工作日: `['1997年1月25日', '1997年2月22日', '1997年3月29日', '1997年4月26日', '1997年5月31日', '1997年6月28日', '1997年7月26日', '1997年8月30日', '1997年9月27日', '1997年10月25日']`