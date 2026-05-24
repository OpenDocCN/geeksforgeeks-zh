# 计算从 L 开始的 [L, R] 范围内连续数字的偶数和奇数位异或

> 原文: [https://www.geeksforgeeks.org/count-even-and-odd-bitwise-xors-in-a-range-l-r/](https://www.geeksforgeeks.org/count-even-and-odd-bitwise-xors-in-a-range-l-r/)

给定两个整数 `L` 和 `R`，任务是从 `L` 开始，从范围 `[L, R]` 中找出连续数字的偶、奇[按位异或](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/)值的个数。

### 示例

> **输入:** `L = 2`，`R = 7`
> **输出:** 偶数= 3，奇数= 3
> **解释:** 取连续数的按位异或:
> 2
> 2 ^ 3 = 1
> 2 ^ 3 ^ 4 = 5
> 2 ^ 3 ^ 4 ^ 5 = 0
> 2 ^ 3 ^ 4 ^ 5 ^ 6 = 6
> 2 ^ 3 ^ 4 ^ 5 ^ 6 ^ 7 = 1
> 因此，得到的按位异或值为{2, 1, 5, 0, 6, 1}。
> 因此，偶数异或值的计数为 3，奇数异或值为 3。

> **输入:** `L = 1`，`R = 7`
> **输出:** 偶数= 3，奇数= 4

### 天真法

最简单的方法是[遍历 `[L, R]` 范围内的所有数字](https://www.geeksforgeeks.org/loops-in-c-and-cpp/)，对从 `L` 开始的连续数字进行**按位异或**。最后，统计得到的偶数和奇数位异或值的个数。

**时间复杂度:** `O(R–L)`
**辅助空间:** `O(1)`

### 高效方法

为了优化上述方法，其思想基于以下观察: 从 `1` 到 `N` 的[逐位异或可以在恒定时间内计算:](https://www.geeksforgeeks.org/calculate-xor-1-n/)

*   除以 `4`，求 `N` 的余数。
*   如果得到的余数是 `0`，那么异或等于 `N`。
*   如果得到的余数是 `1`，那么异或等于 `1`。
*   如果得到的余数是 `2`，那么异或等于 `N + 1`。
*   如果得到的余数是 `3`，那么得到的异或将是 `0`。

从上面的观察可以得出结论，偶数异或值不是 `0` 就是 `4` 的倍数。按照以下步骤解决问题:

*   将 `[L, R]` 范围内的元素数量存储在一个变量中，比如 `X`。
*   通过将 `X` 除以 `4` 并乘以 `2` 将偶数异或值的计数存储在一个变量中，比如 `even`。
*   如果 `L` 为奇数，`X % 4` 等于 `3`，则以 `1` 递增 `even`。
*   否则，如果 `L` 为偶数且 `X % 4` 大于 `0`，则以 `1` 递增 `even`。
*   将奇数异或值的计数存储在变量 `odd = X – even` 中。
*   完成上述步骤后，打印 `even` 和 `odd` 的值作为结果。

下面是上述方法的实现。

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Print count of even and odd numbers
// of XOR value from L to R
void countEvenOdd(int L, int R)
{
    // Store the number of elements
    // between L and R
    int range = R - L + 1;

    // Count of even XOR values
    int even = (range / 4) * 2;

    // If L is odd and range % 4 = 3
    if ((L & 1) && (range % 4 == 3)) {

        // Increment even by 1
        even++;
    }

    // If L is even and range % 4 !=0
    else if (!(L & 1) && (range % 4)) {

        // Increment even by 1
        even++;
    }

    // Print the answer
    cout << "Even = " << even
         << ", Odd = " << range - even;
}

// Driver Code
int main()
{
    int L = 2, R = 7;
    countEvenOdd(L, R);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.io.*;
import java.util.*;

class GFG
{
  // Print count of even and odd numbers
  // of XOR value from L to R
  static void countEvenOdd(int L, int R)
  {

    // Store the number of elements
    // between L and R
    int range = R - L + 1;

    // Count of even XOR values
    int even = (range / 4) * 2;

    // If L is odd and range % 4 = 3
    if ((L & 1) != 0 && (range % 4 == 3))
    {

      // Increment even by 1
      even++;
    }

    // If L is even and range % 4 !=0
    else if ((L & 1) == 0 && (range % 4 != 0))
    {

      // Increment even by 1
      even++;
    }

    // Print the answer
    System.out.print("Even = " + even +
                     ", Odd = " + (range - even));
  }

  // Driver Code
  public static void main(String[] args)
  {
    int L = 2, R = 7;
    countEvenOdd(L, R);
  }
}

// This code is contributed by sanjoy_62.
```

## Python 3

```python
# Python program for the above approach

# Print count of even and odd numbers
# of XOR value from L to R
def countEvenOdd(L, R):

    # Store the number of elements
    # between L and R
    range_val = R - L + 1

    # Count of even XOR values
    even = (range_val // 4) * 2

    # If L is odd and range % 4 = 3
    if ((L & 1) != 0 and (range_val % 4 == 3)):

        # Increment even by 1
        even += 1

    # If L is even and range % 4 !=0
    elif ((L & 1) == 0 and (range_val % 4 != 0)):

        # Increment even by 1
        even += 1

    # Print the answer
    print("Even = " , even ,
          ", Odd = " , (range_val - even))

# Driver Code
if __name__ == '__main__':
    L = 2; R = 7;
    countEvenOdd(L, R)

# This code is contributed by shikhasingrajput
```

## C#

```csharp
// C# program for the above approach
using System;
class GFG
{

    // Print count of even and odd numbers
    // of XOR value from L to R
    static void countEvenOdd(int L, int R)
    {

        // Store the number of elements
        // between L and R
        int range = R - L + 1;

        // Count of even XOR values
        int even = (range / 4) * 2;

        // If L is odd and range % 4 = 3
        if ((L & 1) != 0 && (range % 4 == 3))
        {

            // Increment even by 1
            even++;
        }

        // If L is even and range % 4 !=0
        else if ((L & 1) == 0 && (range % 4 != 0))
        {

            // Increment even by 1
            even++;
        }

        // Print the answer
        Console.Write("Even = " + even +
                      ", Odd = " + (range - even));
    }

  // Driver code
  static void Main()
  {
    int L = 2, R = 7;
    countEvenOdd(L, R);
  }
}

// This code is contributed by divyeshrabadiya07.
```

## JavaScript

```javascript
<script>

// Javascript program for the above approach

// Print count of even and odd numbers
// of XOR value from L to R
function countEvenOdd(L, R)
{
    // Store the number of elements
    // between L and R
    let range = R - L + 1;

    // Count of even XOR values
    let even = parseInt(range / 4) * 2;

    // If L is odd and range % 4 = 3
    if ((L & 1) && (range % 4 == 3)) {

        // Increment even by 1
        even++;
    }

    // If L is even and range % 4 !=0
    else if (!(L & 1) && (range % 4)) {

        // Increment even by 1
        even++;
    }

    // Print the answer
    document.write("Even = " + even
         + ", Odd = " + (range - even));
}

// Driver Code
let L = 2, R = 7;
countEvenOdd(L, R);

</script>
```

**输出:**

```
Even = 3, Odd = 3
```

**时间复杂度:** `O(1)`
**辅助空间:** `O(1)`