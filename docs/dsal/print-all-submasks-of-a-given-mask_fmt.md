# 打印给定掩膜的所有子掩膜

> 原文: [https://www.geeksforgeeks.org/print-all-submasks-of-a-given-mask/](https://www.geeksforgeeks.org/print-all-submasks-of-a-given-mask/)

给定一个整数 `N`，任务是打印由存在于 `N` 的二进制表示中的集合位构成的集合的所有子集。

**示例:**

> **输入:** `N = 5`
> **输出:** `5 4 1`
> **说明:**
> `N` 的二进制表示为“101”，因此所有需要的子集为{“101”、“100”、“001”、“000”}。
>
> **输入:** `N = 25`
> **输出:** `25 24 17 16 9 8 1`
> **说明:**
> `N` 的二进制表示为“11001”。因此，所有必需的子集都是{“11001”、“11000”、“10001”、“10000”、“01001”、“01000”、“0001”、“0000”}。

## 简单方法

最简单的方法是遍历范围内的每个掩码 `[0, 1 << (N 中设置位计数)]`，并检查除了 `N` 中的位之外，是否没有其他位设置在其中。然后，打印出来。

**时间复杂度:** `O(2^(N 中设置位计数))`
**辅助空间:** `O(1)`

## 高效方法

上述方法可以通过仅遍历作为掩码 `N` 的子集的子掩码来优化。

> - 令 `s` 为当前子掩码，它是掩码 `n` 的一个子集。那么可以观察到，通过赋值 `s = (s–1) & n`，可以得到 `n` 的小于 `s` 的下一个子掩码。
> - 在 `s-1` 中，它翻转了 `s` 最右边设置位右侧的所有位，包括 `s` 的最右边设置位。
> - 因此，在与 `n` 进行逐位与（`&`）操作后，就得到了 `n` 的子掩码。
> - 因此，`s = (s–1) & n` 给出了 `n` 的小于 `s` 的下一个子掩码。

**按照以下步骤解决问题:**

1.  初始化一个变量，比如 `S = N`。
2.  在 `S > 0` 时迭代，在每次迭代中，打印 `S` 的值。
3.  赋值 `S = (S–1) & N`。

## 实现

下面是上述方法的实现：

### C++

```cpp
// C++ Program for above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print the submasks of N
void SubMasks(int N)
{
    for (int S = N; S; S = (S - 1) & N) {
        cout << S << " ";
    }
}

// Driver Code
int main()
{
    int N = 25;
    SubMasks(N);

    return 0;
}
```

### Java

```java
// Java Program for above approach
import java.util.*;
class GFG
{

// Function to print the submasks of N
static void SubMasks(int N)
{
    for (int S = N; S > 0; S = (S - 1) & N)
    {
        System.out.print(S + " ");
    }
}

// Driver Code
public static void main(String args[])
{
    int N = 25;
    SubMasks(N);
}
}

// This code is contributed by SURENDRA_GANGWAR.
```

### Python 3

```python
# Python3 program for the above approach

# Function to print the submasks of N
def SubMasks(N) :
    S = N
    while S > 0:
        print(S,end=' ')
        S = (S - 1) & N

# Driven Code
if __name__ == '__main__':
    N = 25
    SubMasks(N)

    # This code is contributed by bgangwar59.
```

### C\#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to print the submasks of N
static void SubMasks(int N)
{
    for (int S = N; S > 0; S = (S - 1) & N)
    {
        Console.Write(S + " ");
    }
}

// Driver Code
static public void Main()
{
    int N = 25;
    SubMasks(N);
}
}

// This code is contributed by Code_hunt.
```

### JavaScript

```javascript
<script>

// JavaScript program of the above approach

// Function to print the submasks of N
function SubMasks(N)
{
    for (let S = N; S > 0; S = (S - 1) & N)
    {
        document.write(S + " ");
    }
}

    // Driver Code

    let N = 25;
    SubMasks(N);

</script>
```

**输出:**

```
25 24 17 16 9 8 1
```

**时间复杂度:** `O(2^(N 中设置位计数))`
**辅助空间:** `O(1)`