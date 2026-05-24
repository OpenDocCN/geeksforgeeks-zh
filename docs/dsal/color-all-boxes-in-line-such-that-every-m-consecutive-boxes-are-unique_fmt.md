# 对所有的盒子进行着色，使得每 M 个连续的盒子都是唯一的

> 原文：[https://www.geeksforgeeks.org/color-all-boxes-in-line-such-that-every-m-consecutive-boxes-are-unique/](https://www.geeksforgeeks.org/color-all-boxes-in-line-such-that-every-m-consecutive-boxes-are-unique/)

给定保持在一条直线上的 `N` 个盒子和 `M` 种颜色，使得 `M ≤ N`。盒子的位置不能改变。任务是找到给盒子上色的方法的数量，这样如果考虑任何 `M` 个连续的盒子组，那么每个盒子的颜色都是唯一的。因为答案可能很大，所以以 `10^9 + 7` 为模打印答案。

## 例

> **输入：** `N = 3`，`M = 2`
> **输出：** `2`
> 如果颜色是 `c1` 和 `c2`，唯一可能的方式是 `{c1，c2，c1}` 和 `{c2，c1，c2}`。
> **输入：** `N = 13`，`M = 10`
> **输出：** `3628800`

## 进路

进路数与 `N` 无关，只取决于 `M`。首先 `M` 个盒子可以用给定的 `M` 种颜色进行着色，无需重复，然后相同的图案可以重复用于下一组 `M` 个盒子。对于颜色的每一种排列都可以这样做。所以，给盒子上色的方式将会是 `M!`。

以下是上述方法的实施：

### C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

#define MOD 1000000007

// Function to return (m! % MOD)
int modFact(int n, int m)
{
    int result = 1;
    for (int i = 1; i <= m; i++)
        result = (result * i) % MOD;

    return result;
}

// Driver code
int main()
{
    int n = 3, m = 2;

    cout << modFact(n, m);

    return 0;
}
```

### Java

```java
// Java implementation of the above approach
class GFG
{
    static final int MOD = 1000000007;

    // Function to return (m! % MOD)
    static int modFact(int n, int m)
    {
        int result = 1;
        for (int i = 1; i <= m; i++)
            result = (result * i) % MOD;

        return result;
    }

    // Driver code
    public static void main (String[] args)
    {
        int n = 3, m = 2;

        System.out.println(modFact(n, m));
    }
}

// This code is contributed by AnkitRai01
```

### Python 3

```python
# Python3 implementation of the approach
MOD = 1000000007

# Function to return (m! % MOD)
def modFact(n, m) :

    result = 1
    for i in range(1, m + 1) :
        result = (result * i) % MOD

    return result

# Driver code
n = 3
m = 2

print(modFact(n, m))

# This code is contributed by
# divyamohan123
```

### C#

```csharp
// C# implementation of the above approach
using System;
class GFG
{
    const int MOD = 1000000007;

    // Function to return (m! % MOD)
    static int modFact(int n, int m)
    {
        int result = 1;
        for (int i = 1; i <= m; i++)
            result = (result * i) % MOD;

        return result;
    }

    // Driver code
    public static void Main()
    {
        int n = 3, m = 2;

        Console.WriteLine(modFact(n, m));
    }
}

// This code is contributed by Nidhi_biet
```

### JavaScript

```javascript
<script>
// Javascript implementation of the approach

const MOD = 1000000007;

// Function to return (m! % MOD)
function modFact(n, m)
{
    let result = 1;
    for (let i = 1; i <= m; i++)
        result = (result * i) % MOD;

    return result;
}

// Driver code
    let n = 3, m = 2;

    document.write(modFact(n, m));

</script>
```

**Output:**

```