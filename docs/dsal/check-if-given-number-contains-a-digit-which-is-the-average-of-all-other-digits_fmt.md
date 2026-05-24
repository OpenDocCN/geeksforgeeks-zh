# 检查给定的数字是否包含所有其他数字的平均值

> 原文: [https://www.geeksforgeeks.org/check-if-given-number-contains-a-digit-which-is-the-average-of-all-other-digits/](https://www.geeksforgeeks.org/check-if-given-number-contains-a-digit-which-is-the-average-of-all-other-digits/)

给定一个整数 `N`，任务是检查 `N` 是否包含一个数字 `D`，使得它是存在于 `N` 中的所有其他数字的平均值。

**示例:**

> **输入:** `N = 132`
> **输出:** 是
> **说明:**
> 因为，`(1 + 3)/2 = 2`。
> **输入:** `N = 436`
> **输出:** 否
> **说明:**
> 不存在这样的数字，它是所有其他数字的平均值。

**方法:**
要解决问题，请按照以下步骤操作:

*   存储 `N` 位数的**和**以及**计数**。
*   将数字存储在[集合](https://www.geeksforgeeks.org/set-in-java/)中。
*   如果 `sum % count` 为 `0`，整数 `sum / count` 出现在集合中，即 `sum / count` 为 `N` 的数字，则打印“是”。否则打印“否”。

以下是上述方法的实现:

## C++

```cpp
// C++ Program to check whether a
// given number contains a digit
// which is the average of all
// other digits
#include <bits/stdc++.h>
using namespace std;

// Function which checks if a
// digits exists in n which
// is the average of all other digits
void check(int n)
{
    set<int> digits;

    int temp = n;
    int sum = 0;
    int count = 0;
    while (temp > 0) {
        // Calculate sum of
        // digits in n
        sum += temp % 10;
        // Store the digits
        digits.insert(temp % 10);
        // Increase the count
        // of digits in n
        count++;
        temp = temp / 10;
    }

    // If average of all digits
    // is an integer
    if (sum % count == 0
        // If the average is a digit
        // in n
        && digits.find(sum / count)
               != digits.end())
        cout << "Yes" << endl;
    // Otherwise
    else
        cout << "No" << endl;
}

// Driver Code
int main()
{
    int n = 42644;
    check(n);
}
```

## Java

```java
// Java program to check whether a
// given number contains a digit
// which is the average of all
// other digits
import java.util.*;

class GFG{

// Function which checks if a
// digits exists in n which
// is the average of all other digits
static void check(int n)
{
    HashSet<Integer> digits = new HashSet<Integer>();

    int temp = n;
    int sum = 0;
    int count = 0;
    while (temp > 0)
    {

        // Calculate sum of
        // digits in n
        sum += temp % 10;

        // Store the digits
        digits.add(temp % 10);

        // Increase the count
        // of digits in n
        count++;
        temp = temp / 10;
    }

    // If average of all digits
    // is an integer
    if (sum % count == 0 &&
        digits.contains(sum / count))
        System.out.print("Yes" + "\n");

    // Otherwise
    else
        System.out.print("No" + "\n");
}

// Driver Code
public static void main(String[] args)
{
    int n = 42644;

    check(n);
}
}

// This code is contributed by Rajput-Ji
```

## Python

```python
# Python3 program to check whether a given
# number contains a digit which is
# the average of all other digits

# Function which checks if a
# digits exists in n which is
# the average of all other digits
def check (n):

    digits = set()

    temp = n
    Sum = 0
    count = 0

    while(temp > 0):

        # Calculate sum of
        # digits in n
        Sum += temp % 10

        # Store digits
        digits.add(temp % 10)

        # Increase the count of
        # digits in n
        count += 1
        temp = temp // 10

    # If average of all digits is integer
    if ((Sum % count == 0) and
        ((int)(Sum / count) in digits)):
        print("Yes")
    else:
        print("No")

# Driver code
n = 42644

# Function calling
check(n)

# This code is contributed by himanshu77
```

## C\#

```csharp
// C# program to check whether a given
// number contains a digit which is the
// average of all other digits
using System;
using System.Collections.Generic;

class GFG{

// Function which checks if a
// digits exists in n which
// is the average of all other digits
static void check(int n)
{
    HashSet<int> digits = new HashSet<int>();

    int temp = n;
    int sum = 0;
    int count = 0;
    while (temp > 0)
    {

        // Calculate sum of
        // digits in n
        sum += temp % 10;

        // Store the digits
        digits.Add(temp % 10);

        // Increase the count
        // of digits in n
        count++;
        temp = temp / 10;
    }

    // If average of all digits
    // is an integer
    if (sum % count == 0 &&
        digits.Contains(sum / count))
        Console.Write("Yes" + "\n");

    // Otherwise
    else
        Console.Write("No" + "\n");
}

// Driver Code
public static void Main(String[] args)
{
    int n = 42644;

    check(n);
}
}

// This code is contributed by Rajput-Ji
```

## JavaScript

```javascript
<script>

// Javascript Program to check whether a
// given number contains a digit
// which is the average of all
// other digits

// Function which checks if a
// digits exists in n which
// is the average of all other digits
function check(n)
{
    var digits = new Set();

    var temp = n;
    var sum = 0;
    var count = 0;
    while (temp > 0) {
        // Calculate sum of
        // digits in n
        sum += temp % 10;
        // Store the digits
        digits.add(temp % 10);
        // Increase the count
        // of digits in n
        count++;
        temp = parseInt(temp / 10);
    }

    // If average of all digits
    // is an integer
    if (sum % count == 0
        // If the average is a digit
        // in n
        && digits.has(sum / count))
        document.write( "Yes" );
    // Otherwise
    else
        document.write( "No" );
}

// Driver Code
var n = 42644;
check(n);

</script>
```

**输出:**

```
Yes
```

*时间复杂度:* `O(log₁₀ N)`