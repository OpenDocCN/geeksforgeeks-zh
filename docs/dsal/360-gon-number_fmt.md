# 360 边数

> 原文: [https://www.geeksforgeeks.org/360-gon-number/](https://www.geeksforgeeks.org/360-gon-number/)

给定一个 `N` 号，任务是找到第 `N` 个 360-gon 数。

> 360 边数是一类图形数。它有一个 360 边的多边形，叫做 360 边。第 `N` 个 360 边数是 360 个数的点，所有其他点被一个公共的共享角包围并形成一个图案。前几个 360 边的数字是 `1，360，1077，2152，3585，5376，…`

### 例:

> **输入:** `N = 2`
> **输出:** `360`
> **说明:**
> 第二个 360-淋病号是 360。
> **输入:** `N = 3`
> **输出:** `1077`

## 方法:

第 `N` 个 360 边数由公式给出:

*   `s` 边多边形的第 `n` 项 = `((s-2)n^2 - (s-4)n)/2`
*   因此 360 边多边形的第 `n` 项为

> `Tn = ((360-2)n^2 - (360-4)n)/2 = (358n^2 - 356n)/2`

以下是上述方法的实现:

### C++

```cpp
// C++ implementation for
// above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the
// nth 360-gon Number
int gonNum360(int n)
{
    return (358 * n * n - 356 * n) / 2;
}

// Driver Code
int main()
{
    int n = 3;
    cout << gonNum360(n);

    return 0;
}
```

### Java

```java
// Java program for above approach
class GFG{

// Function to find the
// nth 360-gon Number
static int gonNum360(int n)
{
    return (358 * n * n - 356 * n) / 2;
}

// Driver code
public static void main(String[] args)
{
    int n = 3;
    System.out.print(gonNum360(n));
}
}

// This code is contributed by shubham
```

### Python 3

```python
# Python3 implementation for
# above approach

# Function to find the
# nth 360-gon Number
def gonNum360(n):

    return (358 * n * n - 356 * n) // 2;

# Driver Code
n = 3;
print(gonNum360(n));

# This code is contributed by Code_Mech
```

### C#

```csharp
// C# program for above approach
using System;
class GFG{

// Function to find the
// nth 360-gon Number
static int gonNum360(int n)
{
    return (358 * n * n - 356 * n) / 2;
}

// Driver code
public static void Main(String[] args)
{
    int n = 3;
    Console.Write(gonNum360(n));
}
}

// This code is contributed by sapnasingh4991
```

### JavaScript

```javascript
<script>

// JavaScript implementation for
// above approach

// Function to find the
// nth 360-gon Number
function gonNum360(n)
{
    return (358 * n * n - 356 * n) / 2;
}

// Driver Code
var n = 3;
document.write(gonNum360(n));

</script>
```

**输出:**

```
1077
```

**参考资料:** [https://en.wikipedia.org/wiki/360-gon](https://en.wikipedia.org/wiki/360-gon)