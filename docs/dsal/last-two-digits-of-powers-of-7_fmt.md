# 7 的最后两位幂

> 原文: [https://www.geeksforgeeks.org/last-two-digits-of-powers-of-7/](https://www.geeksforgeeks.org/last-two-digits-of-powers-of-7/)

给定一个正数 `N`，任务是找到 `7^N` 的最后两位数字。

**举例:**

> **输入:** `N = 5`
> **输出:** `07`
> **说明:**
> `7^5` 的值 = `7 * 7 * 7 * 7 * 7 = 8507`
> 所以，最后两位是 `07`。

> **输入:** `N = 12`
> **输出:** `01`
> **解释:**
> `7^12` 的值 = `13841287201`
> 因此，最后两位是 `01`。

**方法:**
寻找 `X^Y` 最后一个 `K` 数字的一般方法是以对数时间复杂度讨论[这篇](https://www.geeksforgeeks.org/print-last-k-digits-of-ab-a-raised-to-power-b/)文章。在这篇文章中，我们将讨论常数时间解。

以下是对 `7^N` 值的观察，部分 `N` 值:

> `7^1 = 7` 最后两位 = `07`
> `7^2 = 49` 最后两位 = `49`
> `7^3 = 243` 最后两位 = `43`
> `7^4 = 2401` 最后两位 = `01`
> `7^5 = 16807` 最后两位 = `07`
> `7^6 = 117649` 最后两位 = `49`

基于以上观察，我们有以下情况:

1.  如果最后两位数字是 `07`，则 `N = 4K + 3`。
2.  如果最后两位数字是 `49`，则 `N = 4K + 2`。
3.  如果最后两位数字是 `43`，则 `N = 4K + 1`。
4.  如果最后两位数字是 `01`，则 `N = 4K`。

以下是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the last
// two digits of 7^N
string get_last_two_digit(int N)
{
    // Case 4
    if (N % 4 == 0)
        return "01";

    // Case 3
    else if (N % 4 == 1)
        return "07";

    // Case 2
    else if (N % 4 == 2)
        return "49";

    // Case 1
    return "43";
}

// Driver Code
int main()
{
    // Given Number
    int N = 12;

    // Function Call
    cout << get_last_two_digit(N);
    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.io.*;
import java.util.*;

class GFG{

    // Function to find the last
    // two digits of 7^N
    public static String get_last_two_digit(int N)
    {
        // Case 4
        if (N % 4 == 0)
            return "01";

        // Case 3
        else if (N % 4 == 1)
            return "07";

        // Case 2
        else if (N % 4 == 2)
            return "49";

        // Case 1
        return "43";
    }

    // Driver code
    public static void main(String[] args)
    {
        int N = 12;

        // Function Call
        System.out.println(get_last_two_digit(N));
    }
}

// This code is contributed by grand_master
```

## Python 3

```python
# Python3 program for the above approach

# Function to find the last
# two digits of 7 ^ N
def get_last_two_digit(N):

    # Case 4
    if (N % 4 == 0):
        return "01"

    # Case 3
    elif (N % 4 == 1):
        return "07"

    # Case 2
    elif (N % 4 == 2):
        return "49"

    # Case 1
    return "43"

# Driver Code

# Given number
N = 12

# Function call
print(get_last_two_digit(N))

# This code is contributed by grand_master
```

## C\#

```csharp
// C# program for the above approach
using System;

namespace GFG{
class GFG{

    // Function to find the last
    // two digits of 7^N
    public static String get_last_two_digit(int N)
    {
        // Case 4
        if (N % 4 == 0)
            return "01";

        // Case 3
        else if (N % 4 == 1)
            return "07";

        // Case 2
        else if (N % 4 == 2)
            return "49";

        // Case 1
        return "43";
    }

    // Driver code
    public static void Main()
    {
        // Given number
        int N = 12;

        // Function Call
        Console.Write(get_last_two_digit(N));
    }
}
}

// This code is contributed by grand_master
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach

// Function to find the last
// two digits of 7^N
function get_last_two_digit(N)
{
    // Case 4
    if (N % 4 == 0)
        return "01";

    // Case 3
    else if (N % 4 == 1)
        return "07";

    // Case 2
    else if (N % 4 == 2)
        return "49";

    // Case 1
    return "43";
}

// Driver code
var N = 12;

// Function Call
document.write(get_last_two_digit(N));

// This code contributed by gauravrajput1
</script>
```

### Output:

```
01
```

### 时间复杂度与空间复杂度

**时间复杂度:** `O(1)`
**辅助空间:** `O(1)`