# 按升序对日期字符串数组进行排序

> 原文：[https://www.geeksforgeeks.org/sort-an-array-of-string-of-dates-in-ascending-order/](https://www.geeksforgeeks.org/sort-an-array-of-string-of-dates-in-ascending-order/)

## 问题描述

给定一组字符串`dates[]`，任务是按升序对这些日期进行排序。

**注：** 每个日期的形式为`DD mmm yyyy`，其中：

*   `dd` 的域为 `【0-31】`。
*   `mmm` 的域名为 `【Jan, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dec】`。
*   并且，`yyyy` 是一个四位数的整数。

**例：**

> **输入：** `dates[] = {“01 Mar 2015”, “11 Apr 1996”, “22 Oct 2007”}`
> **输出：**
> 11 Apr 1996
> 22 Oct 2007
> 01 Mar 2015
>
> **输入：** `dates[] = {“03 Jan 2018”, “02 Jan 2018”, “04 Jan 2017”}`
> **输出：**
> 04 Jan 2017
> 02 Jan 2018
> 03 Jan 2018

## 方法

从字符串中提取`日`、`月`和`年`作为子字符串，然后按`年`比较两个字符串。如果两个日期的年相等，则比较它们的`月`。如果月份也相等，则`天`将决定日历中哪个日期出现得更早。

以下是上述方法的实施：

## C++ 实现

```cpp
// C++ program to sort the dates in a string array
#include <bits/stdc++.h>
using namespace std;

// Map to store the numeric value of each month depending on
// its occurrence i.e. Jan = 1, Feb = 2 and so on.
unordered_map<string, int> monthsMap;

// Function which initializes the monthsMap
void sort_months()
{
    monthsMap["Jan"] = 1;
    monthsMap["Feb"] = 2;
    monthsMap["Mar"] = 3;
    monthsMap["Apr"] = 4;
    monthsMap["May"] = 5;
    monthsMap["Jun"] = 6;
    monthsMap["Jul"] = 7;
    monthsMap["Aug"] = 8;
    monthsMap["Sep"] = 9;
    monthsMap["Oct"] = 10;
    monthsMap["Nov"] = 11;
    monthsMap["Dec"] = 12;
}

// Comparator function to sort an array of dates
bool comp(string a, string b)
{
    // Comparing the years
    string str1 = a.substr(7, 5);
    string str2 = b.substr(7, 5);
    if (str1.compare(str2) != 0) {
        if (str1.compare(str2) < 0)
            return true;
        return false;
    }

    // Comparing the months
    string month_sub_a = a.substr(3, 3);
    string month_sub_b = b.substr(3, 3);

    // Taking numeric value of months from monthsMap
    int month_a = monthsMap[month_sub_a];
    int month_b = monthsMap[month_sub_b];
    if (month_a != month_b) {
        return month_a < month_b;
    }

    // Comparing the days
    string day_a = a.substr(0, 2);
    string day_b = b.substr(0, 2);
    if (day_a.compare(day_b) < 0)
        return true;
    return false;
}

// Utility function to print the contents
// of the array
void printDates(string dates[], int n)
{
    for (int i = 0; i < n; i++) {
        cout << dates[i] << endl;
    }
}

// Driver code
int main()
{
    string dates[] = { "24 Jul 2017", "25 Jul 2017", "11 Jun 1996",
                       "01 Jan 2019", "12 Aug 2005", "01 Jan 1997" };
    int n = sizeof(dates) / sizeof(dates[0]);

    // Order the months
    sort_months();

    // Sort the dates
    sort(dates, dates + n, comp);

    // Print the sorted dates
    printDates(dates, n);
}
```

## Python 实现

```python
# Python3 program to sort the dates in a string array

# Map to store the numeric value of each month depending on
# its occurrence i.e. Jan = 1, Feb = 2 and so on.
monthsMap = dict()

# Function which initializes the monthsMap
def sort_months():
    monthsMap["Jan"] = 1
    monthsMap["Feb"] = 2
    monthsMap["Mar"] = 3
    monthsMap["Apr"] = 4
    monthsMap["May"] = 5
    monthsMap["Jun"] = 6
    monthsMap["Jul"] = 7
    monthsMap["Aug"] = 8
    monthsMap["Sep"] = 9
    monthsMap["Oct"] = 10
    monthsMap["Nov"] = 11
    monthsMap["Dec"] = 12

def cmp(date):
    date = date.split()
    return int(date[2]), monthsMap[date[1]], int(date[0])

# Utility function to print the contents
# of the array
def printDates(dates, n):
    for i in range(n):
        print(dates[i])

# Driver code
if __name__ == '__main__':
    dates = ["24 Jul 2017", "25 Jul 2017", "11 Jun 1996",
             "01 Jan 2019", "12 Aug 2005", "01 Jan 1997"]
    n = len(dates)

    # Order the months
    sort_months()

    # Sort the dates
    dates.sort(key=cmp)

    # Print the sorted dates
    printDates(dates, n)

# This code is contributed by Amartya Ghosh
```

## 输出

```
11 Jun 1996
01 Jan 1997
12 Aug 2005
24 Jul 2017
25 Jul 2017
01 Jan 2019
```

**时间复杂度：** `O(N * log(N))`
**辅助空间：** `O(1)`