# 第二个六边形数字

> 原文: [https://www.geeksforgeeks.org/second-hexagonal-numbers/](https://www.geeksforgeeks.org/second-hexagonal-numbers/)

第二个六边形数字系列可以表示为

> 3, 10, 21, 36, 55, 78, 105, 136, 171, 210, 253, … ..

## 第 n 项

给定一个整数 `N`。任务是找到给定数列的第 `N` 项。

## 示例

> **输入:** `N = 1`
> **输出:** 3
> **输入:** `N = 4`
> **输出:** 36

## 方法

思路是找到第二个六边形数的通称。下面是第二个六边形数字的一般术语的计算:

> 第一项= 1 * (2*1 + 1) = 3
> 第二项= 2 * (2*2 + 1) = 10
> 第三项= 3 * (2*3 + 1) = 21
> 第四项= 4 * (2*4 + 1) = 36
> 。
> 。
> 。
> 第 n 项= n * (2*n + 1)
> 因此，级数的第 n 项给出如下
>
> `n * (2*n + 1)`

以下是上述方法的实现:

### C++

```cpp
// C++ implementation to
// find N-th term
// in the series
#include <iostream>
#include <math.h>
using namespace std;

// Function to find N-th term
// in the series
void findNthTerm(int n)
{
    cout << n * (2 * n + 1) << endl;
}

// Driver code
int main()
{
    int N = 4;
    findNthTerm(N);

    return 0;
}
```

### Java

```java
// Java implementation to
// find N-th term
// in the series
class GFG{

// Function to find N-th term
// in the series
static void findNthTerm(int n)
{
    System.out.print(n * (2 * n + 1));
}

// Driver code
public static void main (String[] args)
{
    int N = 4;
    findNthTerm(N);
}
}

// This code is contributed by Ritik Bansal
```

### Python 3

```python
# Python3 implementation to
# find N-th term
# in the series

# Function to find N-th term
# in the series
def findNthTerm(n):
    print(n * (2 * n + 1))

# Driver code
N = 4

# Function call
findNthTerm(N)

# This code is contributed by Vishal Maurya
```

### C#

```csharp
// C# implementation to
// find N-th term
// in the series
using System;
class GFG{

// Function to find N-th term
// in the series
static void findNthTerm(int n)
{
    Console.Write(n * (2 * n + 1));
}

// Driver code
public static void Main()
{
    int N = 4;
    findNthTerm(N);
}
}

// This code is contributed by Code_Mech
```

### JavaScript

```javascript
<script>

// Javascript implementation to
// find N-th term
// in the series

// Function to find N-th term
// in the series
function findNthTerm(n)
{
    document.write(n * (2 * n + 1));
}

// Driver code
N = 4;
findNthTerm(N);

</script>
```

**输出:** 36

**时间复杂度:** `O(1)`
**辅助空间:** `O(1)`

**参考:** [OEIS](https://oeis.org/)