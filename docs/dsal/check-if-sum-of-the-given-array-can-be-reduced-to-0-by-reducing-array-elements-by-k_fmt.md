# 检查给定数组的和是否可以通过将数组元素减少 K 来减少到 0

> 原文: [https://www.geeksforgeeks.org/check-if-sum-of-the-given-array-can-be-reduced-to-0-by-reducing-array-elements-by-k/](https://www.geeksforgeeks.org/check-if-sum-of-the-given-array-can-be-reduced-to-0-by-reducing-array-elements-by-k/)

给定一个由 `N` 个整数和一个整数 `K` 组成的数组 `arr[]`，任务是检查数组的和是否可以通过将数组元素减去 `K` 任意次数而减少为 0。

**示例:**

> **输入:** `arr[] = {-3, 2, -1, 5, 1}`，`K = 2`
> **输出:** 是
> **说明:**
> 数组之和为 4。因此，将任意索引处的两个元素减 `K` (= 2)，使数组的和为 0。
> **输入:** `arr[] = {1, -6, 2, 2}`，`K = 1`
> **输出:** 否

**方法:** 按照以下步骤解决问题:

1.  遍历数组并计算给定数组的和。
2.  根据 `sum` 的值，出现以下情况:
    1.  如果 `sum = 0`: 不需要操作。因此，答案是“是的”。
    2.  如果 `sum > 0`: `Sum` 只有在 `sum` 是 `K` 的倍数时，才能化简为 `0`。如果 `sum` 不是 `K` 的倍数，则打印“否”。否则，打印“是”。
    3.  如果 `sum < 0`: 只需打印“否”。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check if the
// sum can be made 0 or not
int sumzero(int arr[], int N, int K)
{
    // Stores sum of array elements
    int sum = 0;

    // Traverse the array
    for (int i = 0; i < N; i++) {

        sum += arr[i];
    }

    if (sum == 0)
        cout << "Yes";

    else if (sum > 0) {

        if (sum % K == 0)
            cout << "Yes";

        else
            cout << "No";
    }

    else
        cout << "No";
    return 0;
}

// Driver Code
int main()
{
    int K, N;

    // Given array arr[]
    int arr1[] = { 1, -6, 2, 2 };
    K = 1;
    N = sizeof(arr1) / sizeof(arr1[0]);

    sumzero(arr1, N, K);

    return 0;
}
```

## Java

```java
// Java program for the above approach

import java.util.*;

class GFG{

// Function to check if the
// sum can be made 0 or not
static int sumzero(int arr[], int N, int K)
{
    // Stores sum of array elements
    int sum = 0;

    // Traverse the array
    for (int i = 0; i < N; i++) {

        sum += arr[i];
    }

    if (sum == 0)
        System.out.print("Yes");

    else if (sum > 0) {

        if (sum % K == 0)
            System.out.print("Yes");

        else
            System.out.print("No");
    }

    else
        System.out.print("No");
    return 0;
}

// Driver Code
public static void main(String[] args)
{
    int K, N;

    // Given array arr[]
    int arr1[] = { 1, -6, 2, 2 };
    K = 1;
    N = arr1.length;

    sumzero(arr1, N, K);

}
}

// This code is contributed by 29AjayKumar
```

## Python 3

```python
# Python3 program for the above approach

# Function to check if the
# sum can be made 0 or not
def sumzero(arr, N, K) :

    # Stores sum of array elements
    sum = 0;

    # Traverse the array
    for i in range(N) :
        sum += arr[i];
    if (sum == 0) :
        print("Yes");
    elif (sum > 0) :
        if (sum % K == 0) :
            print("Yes");
        else :
            print("No");
    else :
        print("No");

# Driver Code
if __name__ == "__main__" :

    # Given array arr[]
    arr1 = [ 1, -6, 2, 2 ];

    K = 1;
    N = len(arr1);

    sumzero(arr1, N, K);

    # This code is contributed by AnkThon
```

## C#

```csharp
// C# program for the above approach
using System;
class GFG{

// Function to check if the
// sum can be made 0 or not
static int sumzero(int []arr, int N, int K)
{

    // Stores sum of array elements
    int sum = 0;

    // Traverse the array
    for (int i = 0; i < N; i++)
    {

        sum += arr[i];
    }

    if (sum == 0)
        Console.Write("Yes");

    else if (sum > 0)
    {

        if (sum % K == 0)
            Console.Write("Yes");

        else
            Console.Write("No");
    }

    else
        Console.Write("No");
    return 0;
}

// Driver Code
public static void Main(String[] args)
{
    int K, N;

    // Given array []arr
    int []arr1 = { 1, -6, 2, 2 };
    K = 1;
    N = arr1.Length;

    sumzero(arr1, N, K);
}
}

// This code is contributed by 29AjayKumar
```

## JavaScript

```javascript
<script>

// JavaScript program for the above approach

// Function to check if the
    // sum can be made 0 or not
    function sumzero(arr , N , K)
    {
        // Stores sum of array elements
        var sum = 0;

        // Traverse the array
        for (i = 0; i < N; i++) {

            sum += arr[i];
        }

        if (sum == 0)
            document.write("Yes");

        else if (sum > 0) {

            if (sum % K == 0)
                document.write("Yes");

            else
                document.write("No");
        }

        else
            document.write("No");
        return 0;
    }

    // Driver Code

        var K, N;

        // Given array arr
        var arr1 = [ 1, -6, 2, 2 ];
        K = 1;
        N = arr1.length;

        sumzero(arr1, N, K);

// This code contributed by gauravrajput1

</script>
```

**输出:**

```
No
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`