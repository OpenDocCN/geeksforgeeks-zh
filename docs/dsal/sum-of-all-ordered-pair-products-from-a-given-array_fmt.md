# 给定数组中所有有序对积的和

> 原文: [https://www.geeksforgeeks.org/sum-of-all-ordered-pair-products-from-a-given-array/](https://www.geeksforgeeks.org/sum-of-all-ordered-pair-products-from-a-given-array/)

给定一个大小为 `N` 的数组 `arr[]`，任务是找出可以从给定数组元素生成的有序对的所有乘积之和。

**例:**

> **输入:** `arr[] = {1, 2, 3}`
> **输出:** 36
> **解释:** 所有可能的对为 `{(1, 1), (1, 2), (1, 3), (2, 1), (2, 2), (2, 3), (3, 1), (3, 2), (3, 3)}`。因此，所有对的乘积之和是 36。
>
> **输入:** `arr[] = {3, 4, 1, 2, 5}`
> **输出:** 225

## 天真方法

最简单的方法是迭代[给定数组中所有可能的对](https://www.geeksforgeeks.org/find-all-pairs-possible-from-the-given-array/)，计算所有对积的乘积之和。

**时间复杂度:** `O(N^2)`
**辅助空间:** `O(1)`

## 高效方法

上述方法可以基于以下观察进行优化:

> `arr[] = {a1, a2, a3, a4, ….., an-1, an}`
> 现在，所有可能对的乘积之和为 =
> {
> `(a1 * a1) + (a1 * a2) + (a1 * a3) + ….. + (a1 * an-1) + (a1 * an) +`
> `(a2 * a1) + (a2 * a2) + (a2 * a3) + ….. + (a2 * an-1) + (a2 * an) +`
> `(a3 * a1) + (a3 * a2) + (a3 * a3) + ….. + (a3 * an-1) + (a3 * an) +`
> …………………………..
> `(an * a1) + (an * a2) + (an * a3) + ….. + (an * an-1) + (an * an)`
>
> = `(a1 + a2 + a3 + ….. + an-1 + an) * (a1 + a2 + a3 + ….. + an-1 + an)`
> = `(a1 + a2 + a3 + ….. + an-1 + an)^2`

按照以下步骤解决问题:

1.  初始化变量 `res = 0` 以存储数组元素的[和](https://www.geeksforgeeks.org/program-find-sum-elements-given-array/)。
2.  [遍历数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/) `arr[]`，并将数组的每个元素添加到 `res` 中。
3.  最后，打印 `res` 的正方形作为所需答案。

下面是上述方法的实现:

### C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to calculate the
// sum of all pair-products
int sumOfProd(int arr[], int N)
{
    // Stores sum of array
    int sum = 0;

    for (int i = 0; i < N; i++) {

        // Update sum of the array
        sum += arr[i];
    }

    return sum * sum;
}

// Driver Code
int main()
{
    int arr[] = { 2, 3, 1, 5, 4 };
    int N = sizeof(arr) / sizeof(arr[0]);
    cout << sumOfProd(arr, N);
    return 0;
}
```

### Java

```java
// Java program to implement
// the above approach
import java.util.*;

class GFG{

// Function to calculate the
// sum of all pair-products
static int sumOfProd(int arr[], int N)
{

    // Stores sum of array
    int sum = 0;

    for(int i = 0; i < N; i++)
    {

        // Update sum of the array
        sum += arr[i];
    }
    return sum * sum;
}

// Driver code
public static void main(String[] args)
{
    int arr[] = { 2, 3, 1, 5, 4 };
    int N = arr.length;

    System.out.print(sumOfProd(arr, N));
}
}

// This code is contributed by offbeat
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to calculate the
# sum of all pair-products
def sumOfProd(arr, N):

    # Stores sum of array
    sum = 0

    for i in range(N):

        # Update sum of the array
        sum += arr[i]

    return sum * sum

# Driver Code
if __name__ == '__main__':

    arr = [ 2, 3, 1, 5, 4 ]
    N = len(arr)

    print(sumOfProd(arr, N))

# This code is contributed by SURENDRA_GANGWAR
```

### C#

```csharp
// C# program to implement
// the above approach
using System;

class GFG{

// Function to calculate the
// sum of all pair-products
static int sumOfProd(int[] arr, int N)
{

    // Stores sum of array
    int sum = 0;

    for(int i = 0; i < N; i++)
    {

        // Update sum of the array
        sum += arr[i];
    }
    return sum * sum;
}

// Driver code
static void Main()
{
    int[] arr = { 2, 3, 1, 5, 4 };
    int N = arr.Length;

    Console.WriteLine(sumOfProd(arr, N));
}
}

// This code is contributed by divyeshrabadiya07
```

### JavaScript

```javascript
<script>

// JavaScript program for the above approach

// Function to calculate the
// sum of all pair-products
function sumOfProd(arr, N)
{

    // Stores sum of array
    let sum = 0;

    for(let i = 0; i < N; i++)
    {

        // Update sum of the array
        sum += arr[i];
    }
    return sum * sum;
}

// Driver Code

let arr = [ 2, 3, 1, 5, 4 ];
let N = arr.length;

document.write(sumOfProd(arr, N));

// This code is contributed by souravghosh0416.
</script>
```

**输出:**

```
225
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`