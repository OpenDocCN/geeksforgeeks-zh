# 求数列 4、11、30、85、248 的第 n 项

> 原文: [https://www.geeksforgeeks.org/find-the-nth-term-of-the-series-4-11-30-85-248/](https://www.geeksforgeeks.org/find-the-nth-term-of-the-series-4-11-30-85-248/)

给定正整数 `N`。任务是找到该系列的第 n 个术语：
> 4, 11, 30, 85, 248…

**示例:**

> **输入:** `N = 4`
> **输出:** 85
>
> **输入:** `N = 2`
> **输出:** 11

**进场:**

给定级数的第 n 项可以概括为:
> `T_N = 3^N + N`

插图:

> **输入:** `N = 4`
> **输出:** 85
> **解释:**
> `T_N = 3^N + N`
> `= 3^4 + 4`
> `= 81 + 4`
> `= 85`

下面是上述问题的实现:

## C++

```cpp
// C++ program to find N-th term
// of the series-
// 4, 11, 30, 85, 248...
#include <bits/stdc++.h>
using namespace std;

// Function to return Nth term
// of the series
int nthTerm(int N)
{
    return pow(3, N) + N;
}

// Driver Code
int main()
{
    // Get the value of N
    int N = 4;
    cout << nthTerm(N);
    return 0;
}
```

**Output**

```
85
```

**时间复杂度:** `O(1)`

**辅助空间:** `O(1)`