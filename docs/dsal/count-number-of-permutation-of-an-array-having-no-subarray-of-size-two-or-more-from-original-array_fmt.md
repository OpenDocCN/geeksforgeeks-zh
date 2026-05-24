# 从原始数组中计算没有大小为 2 或更大的子数组的数组的排列数

> 原文: [https://www.geeksforgeeks.org/count-number-of-permutation-of-an-array-having-no-subarray-of-size-two-or-more-from-original-array/](https://www.geeksforgeeks.org/count-number-of-permutation-of-an-array-having-no-subarray-of-size-two-or-more-from-original-array/)

给定一个由**不同的**整数 `A` 组成的数组，任务是计算给定数组 `A[]` 的可能排列数，使得这些排列不包含原始数组中任何大小为 2 或更大的子数组。

## 示例

> **输入:** `A = [1, 3, 9]`
> **输出:** 3
> 所有 `[1, 3, 9]` 的排列都是: `[1, 3, 9]`，`[1, 9, 3]`，`[3, 9, 1]`，`[3, 1, 9]`，`[9, 1, 3]`，`[9, 3, 1]`
> 这里 `[1, 3, 9]`，`[9, 1, 3]` 因为包含子数组 `[1, 3]` 从原始列表中删除，
> 和 `[3, 9, 1]` 因为它包含来自原始列表的子数组 `[3, 9]`，因此，
> 以下是满足条件的 3 个数组: `[1, 9, 3]`，`[3, 1, 9]`，`[9, 3, 1]`
> **输入:** `A = [1, 3, 9, 12]`
> **输出:** 11

## 朴素方法

遍历所有排列的列表，从 `A` 中移除包含任何子数组 `[i, i+1]` 的那些数组。
以下是上述方法的实现:

### Python 3

```python
# Python implementation of the approach

# Importing the itertools
from itertools import permutations

# Function that return count of all the permutation
# having no sub-array of [ i, i + 1 ]
def count(arr):
    z = []
    perm = permutations(arr)
    for i in list(perm):
        z.append(list(i))

    q = []
    for i in range(len(arr)-1):
        x, y = arr[i], arr[i + 1]
        for j in range(len(z)):

            # Finding the indexes where x is present
            if z[j].index(x) != len(z[j])-1:

                # If y is present at position of x + 1
                # append into a temp list q
                if z[j][z[j].index(x)+1] == y:
                    q.append(z[j])

    # Removing all the lists that are present
    # in z ( list of all permutations )
    for i in range(len(q)):
         if q[i] in z:
             z.remove(q[i])
    return len(z)

# Driver Code
A = [1, 3, 9]
print(count(A))
```

**输出:**

```
3
```

## 高效解法

对更小尺寸的数组进行解后，我们可以观察到一个模式:
下面的模式生成一个递归:
假设数组 `A` 的长度为 `n`，那么:

```
count(0) = 1
count(1) = 1
count(n) = n * count(n-1) + (n-1) * count(n-2)
```

以下是实施办法:

### C++

```cpp
// C++ implementation of the approach
#include<bits/stdc++.h>
using namespace std;

// Recursive function that returns
// the count of permutation-based
// on the length of the array.
int count(int n)
{
    if(n == 0)
        return 1;
    if(n == 1)
        return 1;
    else
        return (n * count(n - 1)) +
              ((n - 1) * count(n - 2));
}

// Driver Code
int main()
{
    int A[] = {1, 2, 3, 9};

    // length of array
    int n = 4;

    // Output required answer
    cout << count(n - 1);

    return 0;
}

// This code is contributed by Sanjit Prasad
```

### Java

```java
// Java implementation of the approach
import java.util.*;

class GFG
{

// Recursive function that returns
// the count of permutation-based
// on the length of the array.
static int count(int n)
{
    if(n == 0)
        return 1;
    if(n == 1)
        return 1;
    else
        return (n * count(n - 1)) +
              ((n - 1) * count(n - 2));
}

// Driver Code
public static void main(String[] args)
{
    int A[] = {1, 2, 3, 9};

    // length of array
    int n = 4;

    // Output required answer
    System.out.println(count(n - 1));
}
}

// This code is contributed by PrinciRaj1992
```

### Python 3

```python
# Python implementation of the approach

# Recursive function that returns
# the count of permutation-based
# on the length of the array.

def count(n):
    if n == 0:
        return 1
    if n == 1:
        return 1
    else:
        return (n * count(n-1)) + ((n-1) * count(n-2))

# Driver Code
A = [1, 2, 3, 9]
print(count(len(A)-1))
```

### C#

```csharp
// C# implementation of the above approach
using System;

class GFG
{

// Recursive function that returns
// the count of permutation-based
// on the length of the array.
static int count(int n)
{
    if(n == 0)
        return 1;
    if(n == 1)
        return 1;
    else
        return (n * count(n - 1)) +
              ((n - 1) * count(n - 2));
}

// Driver Code
public static void Main(String[] args)
{
    int []A = {1, 2, 3, 9};

    // length of array
    int n = 4;

    // Output required answer
    Console.WriteLine(count(n - 1));
}
}

// This code is contributed by PrinciRaj1992
```

### JavaScript

```javascript
<script>

// JavaScript implementation of the approach

// Recursive function that returns
// the count of permutation-based
// on the length of the array.
function count(n) {
    if (n == 0)
        return 1;
    if (n == 1)
        return 1;
    else
        return (n * count(n - 1)) +
            ((n - 1) * count(n - 2));
}

// Driver Code

let A = [1, 2, 3, 9];

// length of array
let n = 4;

// Output required answer
document.write(count(n - 1));

// This code is contributed by _saurabh_jaiswal

</script>
```

**输出:**

```
11
```

**注:** 以上递推关系可在 [oeis.org](https://oeis.org/A000255) 查询。