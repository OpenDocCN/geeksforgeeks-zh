# 查找 2 到 N 范围内整数的最大 GCD 对

> 原文: [https://www.geeksforgeeks.org/find-pair-with-maximum-gcd-for-integers-in-range-2-to-n/](https://www.geeksforgeeks.org/find-pair-with-maximum-gcd-for-integers-in-range-2-to-n/)

给定一个数字 `N`，任务是在范围 `[2, N]` 内寻找一对整数，使其最大 [GCD](https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/)。

**举例:**

> **输入:** `N = 10`
> **输出:** `5`
> **解释:**
> 所有可能对之间的最大可能 GCD 是 `5`（对于对 `{10, 5}`）。
> **输入:** `N = 13`
> **输出:** `6`
> **解释:**
> 所有可能的对之间的最大可能 GCD 为 `6`（对于对 `{12, 6}`）。

## 进场

按照以下步骤解决问题:

1.  如果 `N` 为偶数，则返回对 `{N, N / 2}`。

> **说明:**
> 如果 `N = 10`，任何一对的最大可能 GCD 为 `5`（对于对 `{5, 10}`）。
> 如果 `N = 20`，任何一对的最大可能 GCD 为 `10`（对于对 `{20, 10}`）。

2.  如果 `N` 为奇数，则返回对 `{N-1, (N-1)/2}`。

> **说明:**
> 如果 `N = 11`，任何一对的最大可能 GCD 为 `5`（对于对 `{5, 10}`）。
> 如果 `N = 21`，任何一对的最大可能 GCD 为 `10`（对于对 `{20, 10}`）。

3.  以下是上述方法的实现:

### C++

```cpp
// C++ Program to find a pair of
// integers less than or equal
// to N such that their GCD
// is maximum
#include <bits/stdc++.h>
using namespace std;

// Function to find the required
// pair whose GCD is maximum
void solve(int N)
{
    // If N is even
    if (N % 2 == 0) {

        cout << N / 2 << " "
             << N << endl;
    }
    // If N is odd
    else {
        cout << (N - 1) / 2 << " "
             << (N - 1) << endl;
    }
}

// Driver Code
int main()
{
    int N = 10;
    solve(N);
    return 0;
}
```

### Java

```java
// Java program to find a pair of
// integers less than or equal
// to N such that their GCD
// is maximum

class GFG{

// Function to find the required
// pair whose GCD is maximum
static void solve(int N)
{

    // If N is even
    if (N % 2 == 0)
    {
        System.out.print(N / 2 + " " +
                         N + "\n");
    }

    // If N is odd
    else
    {
        System.out.print((N - 1) / 2 + " " +
                         (N - 1) + "\n");
    }
}

// Driver Code
public static void main(String[] args)
{
    int N = 10;

    solve(N);
}
}

// This code is contributed by Amit Katiyar
```

### Python 3

```python
# Python3 Program to find a pair
# of integers less than or equal
# to N such that their GCD
# is maximum

# Function to find the required
# pair whose GCD is maximum
def solve(N):

    # If N is even
    if (N % 2 == 0):
        print(N // 2, N)

    # If N is odd
    else :
        print((N - 1) // 2, (N - 1))

# Driver Code
N = 10
solve(N)

# This code is contributed by divyamohan123
```

### C#

```csharp
// C# program to find a pair of
// integers less than or equal
// to N such that their GCD
// is maximum
using System;
class GFG{

// Function to find the required
// pair whose GCD is maximum
static void solve(int N)
{

    // If N is even
    if (N % 2 == 0)
    {
        Console.Write(N / 2 + " " +
                      N + "\n");
    }

    // If N is odd
    else
    {
        Console.Write((N - 1) / 2 + " " +
                      (N - 1) + "\n");
    }
}

// Driver Code
public static void Main(String[] args)
{
    int N = 10;

    solve(N);
}
}

// This code is contributed by shivanisinghss2110
```

### JavaScript

```javascript
<script>

// JavaScript program to find a pair of
// integers less than or equal
// to N such that their GCD
// is maximum

    // Function to find the required
    // pair whose GCD is maximum
    function solve(N) {

        // If N is even
        if (N % 2 == 0) {
            document.write(N / 2 + " " + N + "<br/>");
        }

        // If N is odd
        else {
            document.write((N - 1) / 2 + " " + (N - 1) + "<br/>");
        }
    }

    // Driver Code

        var N = 10;

        solve(N);

// This code is contributed by todaysgaurav

</script>
```

**Output:**

```
5 10
```

*   **时间复杂度:** `O(1)`
*   **辅助空间:** `O(1)`