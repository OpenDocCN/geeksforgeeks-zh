# 求数列 0、4、18、48、100 中的第 N 项

> 原文: [https://www.geeksforgeeks.org/find-n-th-term-in-the-series-0-4-18-48-100/](https://www.geeksforgeeks.org/find-n-th-term-in-the-series-0-4-18-48-100/)

给定一个数列 **0, 4, 18, 48, 100...** 和一个整数 `N`，任务是找到该数列的第 `N` 项。

## 示例

> **输入:** `N = 4`
> **输出:** 48
> **解释:** 如顺序所示，我们可以看到第 4 项是 48。
>
> **输入:** `N = 6`
> **输出:** 180

## 进场思路

考虑以下观察：

> 对于 `N = 2`，第二项为 4，可以表示为 8–4，即 `2^3 – 2^2`。
>
> 对于 `N = 3`，第三项为 18，可以表示为 27–9，即 `3^3 – 3^2`。
>
> 对于 `N = 4`，第四项为 48，可以表示为 64–16，即 `4^3 – 4^2`。
>
> ...
>
> 同样，本数列的第 `N` 项可以表示为 `N^3 – N^2`。

所以对于任何一个 `N`，找到 `N` 的平方，然后从这个数的立方中减去它。

下面是上述方法的实现：

### C++

```cpp
// C++ code to find Nth term of series
// 0, 4, 18, ...

#include <bits/stdc++.h>
using namespace std;

// Function to find N-th term
// of the series
int getNthTerm(int N)
{
    // (pow(N, 3) - pow(N, 2))
    return (N * N * N) - (N * N);
}

// Driver Code
int main()
{
    int N = 4;

    // Get the 8th term of the series
    cout << getNthTerm(N);
    return 0;
}
```

### Java

```java
// Java code to find Nth term of series
// 0, 4, 18, ...
class GFG
{

    // Function to find N-th term
    // of the series
    public static int getNthTerm(int N)
    {

        // (pow(N, 3) - pow(N, 2))
        return (N * N * N) - (N * N);
    }

    // Driver Code
    public static void main(String args[])
    {
        int N = 4;

        // Get the 8th term of the series
        System.out.println(getNthTerm(N));
    }
}

// This code is contributed by gfgking
```

### Python 3

```python
# Python code to find Nth term of series
# 0, 4, 18, ...

# Function to find N-th term
# of the series
def getNthTerm(N):

    # (pow(N, 3) - pow(N, 2))
    return (N * N * N) - (N * N);

# Driver Code
N = 4;

# Get the 8th term of the series
print(getNthTerm(N));

# This code is contributed by gfgking
```

### C#

```csharp
// C# code to find Nth term of series
// 0, 4, 18, ...

using System;
class GFG {
    // Function to find N-th term
    // of the series
    public static int getNthTerm(int N) {
        // (pow(N, 3) - pow(N, 2))
        return (N * N * N) - (N * N);
    }

    // Driver Code
    public static void Main() {
        int N = 4;

        // Get the 8th term of the series
        Console.Write(getNthTerm(N));
    }
}

// This code is contributed by gfgking
```

### JavaScript

```javascript
<script>
// Javascript code to find Nth term of series
// 0, 4, 18, ...

// Function to find N-th term
// of the series
function getNthTerm(N) {
    // (pow(N, 3) - pow(N, 2))
    return (N * N * N) - (N * N);
}

// Driver Code

let N = 4;

// Get the 8th term of the series
document.write(getNthTerm(N));
// This code is contributed by gfgking
</script>
```

**输出**

```
48
```

**时间复杂度:** `O(1)`
**辅助空间:** `O(1)`