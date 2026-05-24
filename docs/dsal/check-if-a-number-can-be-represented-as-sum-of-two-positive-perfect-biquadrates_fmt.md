# 检查一个数是否可以表示为两个正完美双二次曲线的和

> 原文: [https://www.geeksforgeeks.org/check-if-a-number-can-be-represented-as-sum-of-two-positive-perfect-biquadrates/](https://www.geeksforgeeks.org/check-if-a-number-can-be-represented-as-sum-of-two-positive-perfect-biquadrates/)

给定一个正整数 `N`，任务是检查 `N` 是否可以写成两个完美双二次曲线之和，即 `N = X^4 + Y^4`，其中 `X` 和 `Y` 为非负整数。如果可能，则打印`是`。否则，打印`否`。

**示例:**

> **输入:** `N = 97`
> **输出:** 是
> **说明:** 2 和 3 的双二次曲线之和为 97，即 `2^4 + 3^4 = 16 + 81 = 97` (= `N`)。
>
> **输入:** `N = 7857`
> **输出:** 是

## 天真的方法

解决给定问题最简单的方法是考虑整数 `X` 和 `Y` 的所有可能组合，并检查它们的[双二次曲线](https://en.wiktionary.org/wiki/biquadrate)之和是否等于 `N`。如果发现为真，则打印`是`。否则，打印`否`。

**时间复杂度:** `O(sqrt(N))`
**辅助空间:** `O(1)`

## 高效方法

上述方法也可以通过使用[双指针方法](https://www.geeksforgeeks.org/two-pointers-technique/)进行优化，思路是在 `(0, \sqrt[4]{N})` 范围内找到这两个数字。请按照以下步骤解决此问题:

*   初始化两个指针，设 `i` 为 `0` 和 `j` 为 `\sqrt[4]{N}`。
*   [循环](https://www.geeksforgeeks.org/range-based-loop-c/)直到 `j` 小于 `i`，执行以下步骤:
    *   如果 `j^4` 的值为 `N` 或 `i^4` 的值为 `N`，则打印`是`。
    *   如果 `(i^4 + i^4)` 或 `(j^4 + j^4)` 或 `(i^4 + j^4)` 的值为 `N`，则打印`是`。
    *   如果 `(i^4 + j^4)` 的值小于 `N`，则将指针 `i` 增加 `1`。否则，将指针 `j` 减少 `1`。
*   完成上述步骤后，如果循环终止，则打印`否`，因为不存在满足给定标准的对。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if the given number
// N can be expressed as the sum of two
// biquadrates or not
string sumOfTwoBiquadrates(int N)
{
    // Base Case
    if (N == 0)
        return "Yes";

    // Find the range to traverse
    int j = floor(sqrt(sqrt(N)));
    int i = 1;

    while (i <= j) {

        // If x & y exists
        if (j * j * j * j == N)
            return "Yes";
        if (i * i * i * i == N)
            return "Yes";
        if (i * i * i * i
                + j * j * j * j
            == N)
            return "Yes";

        // If sum of powers of i and j
        // of 4 is less than N, then
        // increment the value of i
        if (i * i * i * i
                + j * j * j * j
            < N)
            i++;

        // Otherwise, decrement the
        // value of j
        else
            j--;
    }

    // If no such pairs exist
    return "No";
}

// Driver Code
int main()
{
    int N = 7857;
    cout << sumOfTwoBiquadrates(N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
public class GFG
{

// Function to check if the given number
// N can be expressed as the sum of two
// biquadrates or not
static String sumOfTwoBiquadrates(int N)
{

    // Base Case
    if (N == 0)
        return "Yes";

    // Find the range to traverse
    int j = (int)Math.floor((double)(Math.sqrt((int)(Math.sqrt(N)))));

    int i = 1;

    while (i <= j) {

        // If x & y exists
        if (j * j * j * j == N)
            return "Yes";
        if (i * i * i * i == N)
            return "Yes";
        if (i * i * i * i
                + j * j * j * j
            == N)
            return "Yes";

        // If sum of powers of i and j
        // of 4 is less than N, then
        // increment the value of i
        if (i * i * i * i
                + j * j * j * j
            < N)
            i++;

        // Otherwise, decrement the
        // value of j
        else
            j--;
    }

    // If no such pairs exist
    return "No";
}

// Driver Code
public static void main(String []args)
{
    int N = 7857;
    System.out.println(sumOfTwoBiquadrates(N));

}}

// This code is contributed by AnkThon
```

### Python 3

```python
# python program for the above approach
import math

# Function to check if the given number
# N can be expressed as the sum of two
# biquadrates or not
def sumOfTwoBiquadrates(N):

    # Base Case
    if (N == 0):
        return "Yes"

    # Find the range to traverse
    j = int(math.sqrt(math.sqrt(N)))
    i = 1

    while (i <= j):

        # If x & y exists
        if (j * j * j * j == N):
            return "Yes"
        if (i * i * i * i == N):
            return "Yes"
        if (i * i * i * i + j * j * j * j == N):
            return "Yes"

        # If sum of powers of i and j
        # of 4 is less than N, then
        # increment the value of i
        if (i * i * i * i + j * j * j * j < N):
            i += 1

        # Otherwise, decrement the
        # value of j
        else:
            j -= 1

    # If no such pairs exist
    return "No"

# Driver Code
if __name__ == "__main__":

    N = 7857
    print(sumOfTwoBiquadrates(N))

# This code is contributed by rakeshsahni
```

### C#

```csharp
// C# program for the above approach
using System;
class GFG
{

// Function to check if the given number
// N can be expressed as the sum of two
// biquadrates or not
static string sumOfTwoBiquadrates(int N)
{

    // Base Case
    if (N == 0)
        return "Yes";

    // Find the range to traverse
    int j = (int)Math.Floor((double)(Math.Sqrt((int)(Math.Sqrt(N)))));

    int i = 1;

    while (i <= j) {

        // If x & y exists
        if (j * j * j * j == N)
            return "Yes";
        if (i * i * i * i == N)
            return "Yes";
        if (i * i * i * i
                + j * j * j * j
            == N)
            return "Yes";

        // If sum of powers of i and j
        // of 4 is less than N, then
        // increment the value of i
        if (i * i * i * i
                + j * j * j * j
            < N)
            i++;

        // Otherwise, decrement the
        // value of j
        else
            j--;
    }

    // If no such pairs exist
    return "No";
}

// Driver Code
public static void Main()
{
    int N = 7857;
    Console.WriteLine(sumOfTwoBiquadrates(N));

}}

// This code is contributed by ukasp.
```

### JavaScript

```javascript
<script>
// Javascript program for the above approach

// Function to check if the given number
// N can be expressed as the sum of two
// biquadrates or not
function sumOfTwoBiquadrates(N)
{

  // Base Case
  if (N == 0) return "Yes";

  // Find the range to traverse
  let j = Math.floor(Math.sqrt(Math.sqrt(N)));
  let i = 1;

  while (i <= j)
  {

    // If x & y exists
    if (j * j * j * j == N) return "Yes";
    if (i * i * i * i == N) return "Yes";
    if (i * i * i * i + j * j * j * j == N) return "Yes";

    // If sum of powers of i and j
    // of 4 is less than N, then
    // increment the value of i
    if (i * i * i * i + j * j * j * j < N) i++;

    // Otherwise, decrement the
    // value of j
    else j--;
  }

  // If no such pairs exist
  return "No";
}

// Driver Code

let N = 7857;
document.write(sumOfTwoBiquadrates(N));

// This code is contributed by gfgking.
</script>
```

**输出:**

```
Yes
```

**时间复杂度:** `O(\sqrt[4]{N})`
**辅助空间:** `O(1)`