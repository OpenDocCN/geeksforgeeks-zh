# 当 N 除以[1，N]

范围内的所有数字时，不同余数的计数

> 原文:[https://www . geesforgeks . org/count-of-distinct-reminders-when-n 被-1-n 范围内的所有数字除/](https://www.geeksforgeeks.org/count-of-distinct-remainders-when-n-is-divided-by-all-the-numbers-from-the-range-1-n/)

给定一个整数 **N** ，任务是找出当 **N** 除以范围**【1，N】**中的每一个元素时可以得到的不同余数的总数。
**举例:**

> **输入:** N = 5
> **输出:**3
> 5% 1 = 0
> 5% 2 = 1
> 5% 3 = 2
> 5% 4 = 1
> 5% 5 = 0
> 不同的余数是 0、1 和 2。
> **输入:** N = 44
> **输出:** 22

**方法:**很容易观察到，对于 **N** 的偶数，不同余数的数量将为 **N / 2** ,对于 **N** 的奇数，将为 **1 + ⌊N / 2⌋** 。
以下是上述方法的实施:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the count of distinct
// remainders that can be obtained when
// n is divided by every element
// from the range [1, n]
int distinctRemainders(int n)
{

    // If n is even
    if (n % 2 == 0)
        return (n / 2);

    // If n is odd
    return (1 + (n / 2));
}

// Driver code
int main()
{
    int n = 5;

    cout << distinctRemainders(n);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java implementation of the above approach
class GFG
{

// Function to return the count of distinct
// remainders that can be obtained when
// n is divided by every element
// from the range [1, n]
static int distinctRemainders(int n)
{

    // If n is even
    if (n % 2 == 0)
        return (n / 2);

    // If n is odd
    return (1 + (n / 2));
}

// Driver code
public static void main(String[] args)
{
    int n = 5;
    System.out.println(distinctRemainders(n));
}
}

// This code is contributed by Mohit Kumar
```

## 蟒蛇 3

```cpp
# Python3 implementation of the approach

# Function to return the count of distinct
# remainders that can be obtained when
# n is divided by every element
# from the range [1, n]
def distinctRemainders(n):

    # If n is even
    if n % 2 == 0:
        return n//2

    # If n is odd
    return ((n//2)+1)

# Driver code
if __name__=="__main__":

    n = 5
    print(distinctRemainders(n))
```

## C#

```cpp
// C# implementation of the above approach
using System;

class GFG
{

    // Function to return the count of distinct
    // remainders that can be obtained when
    // n is divided by every element
    // from the range [1, n]
    static int distinctRemainders(int n)
    {

        // If n is even
        if (n % 2 == 0)
            return (n / 2);

        // If n is odd
        return (1 + (n / 2));
    }

    // Driver code
    public static void Main()
    {
        int n = 5;
        Console.WriteLine(distinctRemainders(n));
    }
}

// This code is contributed by AnkitRai01
```

## java 描述语言

```cpp
<script>

// Javascript implementation of the approach

// Function to return the count of distinct
// remainders that can be obtained when
// n is divided by every element
// from the range [1, n]
function distinctRemainders(n)
{

    // If n is even
    if (n % 2 == 0)
        return parseInt(n / 2);

    // If n is odd
    return (1 + parseInt(n / 2));
}

// Driver code
    let n = 5;

    document.write(distinctRemainders(n));

</script>
```

**Output:** 

```cpp
3
```

**时间复杂度:** O(1)