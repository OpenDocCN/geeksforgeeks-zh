# 从以星期一为第一天的基准年中找到给定年份的第一天

> 原文：[https://www.geeksforgeeks.org/find-the-first-day-of-a-given-year-from-a-base-year-having-first-day-as-monday/](https://www.geeksforgeeks.org/find-the-first-day-of-a-given-year-from-a-base-year-having-first-day-as-monday/)

给定代表两年的两个整数 `Y` 和 `B`，任务是找到一周中的哪一天是年份 `Y` 的 1 月 1 日，假设年份 `B` 的 1 月 1 日是星期一。

**示例：**

> **输入：**
> `Y = 2020`
> `B = 1900`
> **输出：**
> 周三
> **说明：**
> 01/01/2020 是周三，考虑到 01/01/1900 是周一。
>
> **输入：**
> `Y = 2020`
> `B = 1905`
> **输出：**
> 星期四
> **解释：**
> 2020 年 1 月 1 日是星期三，假设 1905 年 1 月 1 日是星期一。

## 方法

按照以下步骤解决问题：

1.  介于基准年 `B` 和年份 `Y` 之间的总年数等于 `(Y–1)–B`。
2.  介于之间的闰年总数 = 总年数 / 4。
3.  介于之间的非闰年总数 = `总年数 – 闰年`。
4.  总天数 = `总闰年 * 366 + 非闰年 * 365 + 1`。
5.  因此，`Y` 年 1 月 1 日为 `总天数 % 7`。

下面是上述方法的实现：

## C++14

```cpp
// C++ Implementation of
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the day of
// 1st January of Y year
void findDay(int Y, int B)
{
    int lyear, rest, totaldays, day;

    // Count years between
    // years Y and B
    Y = (Y - 1) - B;

    // Count leap years
    lyear = Y / 4;

    // Non leap years
    rest = Y - lyear;

    // Total number of days in the years
    // lying between the years Y and B
    totaldays = (rest * 365)
                + (lyear * 366) + 1;

    // Actual day
    day = (totaldays % 7);

    if (day == 0)
        printf("Monday");

    else if (day == 1)
        printf("Tuesday");

    else if (day == 2)
        printf("Wednesday");

    else if (day == 3)
        printf("Thursday");

    else if (day == 4)
        printf("Friday");

    else if (day == 5)
        printf("Saturday");

    else if (day == 6)
        printf("Sunday");

    else
        printf("INPUT YEAR IS WRONG!");
}

// Driver Code
int main()
{
    int Y = 2020, B = 1900;
    findDay(Y, B);

    return 0;
}
```

## Java

```java
// Java program to implement
// the above approach
import java.util.*;

class GFG
{

  // Function to find the day of
  // 1st January of Y year
  static void findDay(int Y, int B)
  {
    int lyear, rest, totaldays, day;

    // Count years between
    // years Y and B
    Y = (Y - 1) - B;

    // Count leap years
    lyear = Y / 4;

    // Non leap years
    rest = Y - lyear;

    // Total number of days in the years
    // lying between the years Y and B
    totaldays = (rest * 365)
      + (lyear * 366) + 1;

    // Actual day
    day = (totaldays % 7);

    if (day == 0)
      System.out.println("Monday");

    else if (day == 1)
      System.out.println("Tuesday");

    else if (day == 2)
      System.out.println("Wednesday");

    else if (day == 3)
      System.out.println("Thursday");

    else if (day == 4)
      System.out.println("Friday");

    else if (day == 5)
      System.out.println("Saturday");

    else if (day == 6)
      System.out.println("Sunday");

    else
      System.out.println("INPUT YEAR IS WRONG!");
  }

  // Driver code
  public static void main(String[] args)
  {
    int Y = 2020, B = 1900;
    findDay(Y, B);
  }
}

// This code is contributed by code_hunt.
```

## Python 3

```python
# Python program to implement
# the above approach

# Function to find the day of
# 1st January of Y year
def findDay(Y, B):
    lyear, rest, totaldays, day = 0, 0, 0, 0;

    # Count years between
    # years Y and B
    Y = (Y - 1) - B;

    # Count leap years
    lyear = Y // 4;

    # Non leap years
    rest = Y - lyear;

    # Total number of days in the years
    # lying between the years Y and B
    totaldays = (rest * 365) + (lyear * 366) + 1;

    # Actual day
    day = (totaldays % 7);

    if (day == 0):
        print("Monday");

    elif (day == 1):
        print("Tuesday");

    elif (day == 2):
        print("Wednesday");

    elif (day == 3):
        print("Thursday");

    elif (day == 4):
        print("Friday");

    elif (day == 5):
        print("Saturday");

    elif (day == 6):
        print("Sunday");

    else:
        print("INPUT YEAR IS WRONG!");

# Driver code
if __name__ == '__main__':
    Y = 2020; B = 1900;
    findDay(Y, B);

# This code is contributed by 29AjayKumar
```

## C#

```csharp
// C# program to implement
// the above approach
using System;
class GFG
{
  // Function to find the day of
  // 1st January of Y year
  static void findDay(int Y, int B)
  {
    int lyear, rest, totaldays, day;

    // Count years between
    // years Y and B
    Y = (Y - 1) - B;

    // Count leap years
    lyear = Y / 4;

    // Non leap years
    rest = Y - lyear;

    // Total number of days in the years
    // lying between the years Y and B
    totaldays = (rest * 365)
      + (lyear * 366) + 1;

    // Actual day
    day = (totaldays % 7);
    if (day == 0)
      Console.WriteLine("Monday");
    else if (day == 1)
      Console.WriteLine("Tuesday");
    else if (day == 2)
      Console.WriteLine("Wednesday");
    else if (day == 3)
      Console.WriteLine("Thursday");
    else if (day == 4)
      Console.WriteLine("Friday");
    else if (day == 5)
      Console.WriteLine("Saturday");
    else if (day == 6)
      Console.WriteLine("Sunday");
    else
      Console.WriteLine("INPUT YEAR IS WRONG!");
  }

// Driver code
static void Main()
{
    int Y = 2020, B = 1900;
    findDay(Y, B);
}
}

// This code is contribute by susmitakundugoaldanga
```

## JavaScript

```javascript
<script>

// Javascript program of the above approach

  // Function to find the day of
  // 1st January of Y year
  function findDay(Y, B)
  {
    let lyear, rest, totaldays, day;

    // Count years between
    // years Y and B
    Y = (Y - 1) - B;

    // Count leap years
    lyear = Math.floor(Y / 4);

    // Non leap years
    rest = Y - lyear;

    // Total number of days in the years
    // lying between the years Y and B
    totaldays = (rest * 365)
      + (lyear * 366) + 1;

    // Actual day
    day = (totaldays % 7);

    if (day == 0)
      document.write("Monday");

    else if (day == 1)
      document.write("Tuesday");

    else if (day == 2)
      document.write("Wednesday");

    else if (day == 3)
      document.write("Thursday");

    else if (day == 4)
      document.write("Friday");

    else if (day == 5)
      document.write("Saturday");

    else if (day == 6)
      document.write("Sunday");

    else
      document.write("INPUT YEAR IS WRONG!");
  }

    // Driver Code

    // Given array
    let Y = 2020, B = 1900;
    findDay(Y, B);

</script>
```

**输出：**

```
Wednesday
```

**时间复杂度：** `O(1)`
**辅助空间：** `O(1)`