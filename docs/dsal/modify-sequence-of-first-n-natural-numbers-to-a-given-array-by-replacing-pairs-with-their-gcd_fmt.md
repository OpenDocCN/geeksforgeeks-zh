# 通过用其GCD替换对，将前N个自然数的序列修改为给定的数组

> 原文：[https://www.geeksforgeeks.org/modify-sequence-of-first-n-natural-numbers-to-a-given-array-by-replacing-pairs-with-their-gcd/](https://www.geeksforgeeks.org/modify-sequence-of-first-n-natural-numbers-to-a-given-array-by-replacing-pairs-with-their-gcd/)

给定一个整数 `N` 和一个[数组](https://www.geeksforgeeks.org/introduction-to-arrays/) `arr[]`，任务是检查第一个 `N` 自然数的序列，即 `{1, 2, 3, ...}`，通过从序列中选择任意一对 `(i, j)`，并将 `i` 和 `j` 替换为 `i` 和 `j` 的 [GCD](https://www.geeksforgeeks.org/basic-and-extended-euclidean-algorithms/)，可以使序列等于 `arr[]`。如果可能，则打印 `"Yes"`。否则，打印 `"No"`。

**示例：**

> **输入：** `N = 4`, `arr[] = {1, 2, 3, 2}`
> **输出：** `Yes`
> **说明：** 对于序列 `{1, 2, 3, 4}` 中的对 `(2, 4)`，`GCD(2, 4) = 2`。现在，序列修改为 `{1, 2, 3, 2}`，这与 `arr[]` 相同。
>
> **输入：** `N = 3`, `arr[] = {1, 2, 2}`
> **输出：** `No`

## 方法思路

这个想法是基于两个数字的 [GCD](https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/) 位于 `1` 和两个数字的[最小值](https://www.geeksforgeeks.org/find-maximum-and-minimum-of-two-numbers-using-absolute-function/)之间。根据 GCD 的定义，这是两者相除的最大数值。因此，当且仅当某个数是它的因子时，才能使索引处的数变小。因此，可以得出结论，对于数组中的每个 `i`<sup>th</sup> 索引，如果以下条件成立，则数组 `arr[]` 可以从第一个 `N` 自然数的序列中获得。

> `(i + 1) % arr[i] == 0`

按照以下步骤解决问题：

*   [使用变量 `i` 遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/) `arr[]`。
*   对于每个 `i`<sup>th</sup> 指数，检查 `(i + 1) % arr[i]` 是否等于 `0`。如果发现任何数组元素为假，打印 `"No"`。
*   否则，完成数组遍历后，打印 `"Yes"`。

## 代码实现

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check if array arr[]
// can be obtained from first N
// natural numbers or not
void isSequenceValid(vector<int>& B,
                     int N)
{
    for (int i = 0; i < N; i++) {

        if ((i + 1) % B[i] != 0) {
            cout << "No";
            return;
        }
    }

    cout << "Yes";
}

// Driver Code
int main()
{
    int N = 4;
    vector<int> arr{ 1, 2, 3, 2 };

    // Function Call
    isSequenceValid(arr, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
class GFG{

// Function to check if array arr[]
// can be obtained from first N
// natural numbers or not
static void isSequenceValid(int[] B,
                            int N)
{
    for(int i = 0; i < N; i++)
    {
        if ((i + 1) % B[i] != 0)
        {
            System.out.print("No");
            return;
        }
    }
    System.out.print("Yes");
}

// Driver code
public static void main(String[] args)
{
    int N = 4;
    int[] arr = { 1, 2, 3, 2 };

    // Function Call
    isSequenceValid(arr, N);
}
}

// This code is contributed by sanjoy_62
```

### Python

```python
# Python3 program for the above approach

# Function to check if array arr[]
# can be obtained from first N
# natural numbers or not
def isSequenceValid(B, N):

    for i in range(N):
        if ((i + 1) % B[i] != 0):
            print("No")
            return

    print("Yes")

# Driver Code
N = 4
arr = [ 1, 2, 3, 2 ]

# Function Call
isSequenceValid(arr, N)

# This code is contributed by susmitakundugoaldanga
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to check if array arr[]
// can be obtained from first N
// natural numbers or not
static void isSequenceValid(int[] B,
                            int N)
{
    for(int i = 0; i < N; i++)
    {
        if ((i + 1) % B[i] != 0)
        {
            Console.WriteLine("No");
            return;
        }
    }
    Console.WriteLine("Yes");
}

// Driver code
public static void Main()
{
    int N = 4;
    int[] arr = { 1, 2, 3, 2 };

    // Function Call
    isSequenceValid(arr, N);
}
}

// This code is contributed by code_hunt
```

### JavaScript

```javascript
<script>
// Javascript program to implement
// the above approach

// Function to check if array arr[]
// can be obtained from first N
// natural numbers or not
function isSequenceValid(B, N)
{
    for(let i = 0; i < N; i++)
    {
        if ((i + 1) % B[i] != 0)
        {
            document.write("No");
            return;
        }
    }
    document.write("Yes");
}

// Driver code

    let N = 4;
    let arr = [ 1, 2, 3, 2 ];

    // Function Call
    isSequenceValid(arr, N);

    // This code is contributed by souravghosh0416.
</script>
```

**输出：**

```
Yes
```

## 复杂度分析

*   **时间复杂度：** `O(N)`
*   **辅助空间：** `O(1)`