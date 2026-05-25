# 所有数组元素的位数乘积之和

> 原文: [https://www.geeksforgeeks.org/sum-of-the-product-of-digits-of-all-array-elements/](https://www.geeksforgeeks.org/sum-of-the-product-of-digits-of-all-array-elements/)

给定一个数组 `arr`，任务是找出所有数组元素的数字乘积的和。

## 示例

> **输入:** `arr[] = {11, 23, 41}`
> **输出:** `11`
> **解释:** `1*1 + 2*3 + 4*1 = 1 + 6 + 4 = 11`

> **输入:** `arr[] = {46, 32, 78, 0}`
> **输出:** `86`

## 处理方法

要解决这个问题，先求所有数字的位数的乘积，然后把它们加起来就可以了。请按照以下步骤解决此问题:

1.  创建一个函数 `findProduct()`，它将获得一个数字并查找其数字的乘积。
2.  创建一个变量 `sum` 来存储最终答案，并用 0 初始化。
3.  现在，遍历数组，对于每个元素:
    *   传递给函数 `findProduct()`，得到其数字的乘积。
    *   然后将其位数的乘积加到 `sum` 上。
4.  返回 `sum` 作为最终答案。

下面是上述方法的实现:

### C++

```cpp
// C++ code for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the product of the
// digits of a number N
int findProduct(int N)
{
    if (N == 0) {
        return 0;
    }

    int product = 1;
    while (N > 0) {
        product *= (N % 10);
        N /= 10;
    }

    return product;
}

// Function to find the sum of the product of
// digits of all array elements
int sumOfProduct(vector<int> arr)
{

    int sum = 0;
    for (auto x : arr) {
        sum += findProduct(x);
    }

    return sum;
}

// Driver Code
int main()
{
    vector<int> arr = { 46, 32, 78, 0 };
    cout << sumOfProduct(arr);
}
```

### Java

```java
// Java code to implement above approach
import java.util.*;
public class GFG {

// Function to find the product of the
// digits of a number N
static int findProduct(int N)
{
    if (N == 0) {
        return 0;
    }

    int product = 1;
    while (N > 0) {
        product *= (N % 10);
        N /= 10;
    }

    return product;
}

// Function to find the sum of the product of
// digits of all array elements
static int sumOfProduct(int []arr)
{

    int sum = 0;
    for (int i = 0; i < arr.length; i++) {
        sum += findProduct(arr[i]);
    }

    return sum;
}

// Driver code
public static void main(String args[])
{
    int []arr = { 46, 32, 78, 0 };
    System.out.println(sumOfProduct(arr));

}
}

// This code is contributed by Samim Hossain Mondal.
```

### Python 3

```python
# Python code for the above approach

# Function to find the product of the
# digits of a number N
def findProduct(N):
    if (N == 0):
        return 0

    product = 1
    while (N > 0):
        product *= (N % 10)
        N = N // 10
    return product

# Function to find the sum of the product of
# digits of all array elements
def sumOfProduct(arr):

    sum = 0
    for x in arr:
        sum += findProduct(x)

    return sum

# Driver Code
arr = [46, 32, 78, 0]
print(sumOfProduct(arr))

# This code is contributed by Saurabh Jaiswal
```

### C#

```csharp
// C# code to implement above approach
using System;
class GFG {

// Function to find the product of the
// digits of a number N
static int findProduct(int N)
{
    if (N == 0) {
        return 0;
    }

    int product = 1;
    while (N > 0) {
        product *= (N % 10);
        N /= 10;
    }

    return product;
}

// Function to find the sum of the product of
// digits of all array elements
static int sumOfProduct(int []arr)
{

    int sum = 0;
    for (int i = 0; i < arr.Length; i++) {
        sum += findProduct(arr[i]);
    }

    return sum;
}

// Driver code
public static void Main()
{
    int []arr = { 46, 32, 78, 0 };
    Console.Write(sumOfProduct(arr));

}
}

// This code is contributed by Samim Hossain Mondal.
```

### JavaScript

```javascript
<script>
    // JavaScript code for the above approach

    // Function to find the product of the
    // digits of a number N
    function findProduct(N) {
      if (N == 0) {
        return 0;
      }

      let product = 1;
      while (N > 0) {
        product *= (N % 10);
        N = Math.floor(N / 10)
      }
      return product;
    }

    // Function to find the sum of the product of
    // digits of all array elements
    function sumOfProduct(arr) {

      let sum = 0;
      for (let x of arr) {
        sum += findProduct(x);
      }

      return sum;
    }

    // Driver Code
    let arr = [46, 32, 78, 0];
    document.write(sumOfProduct(arr));

  // This code is contributed by Potta Lokesh
  </script>
```

**输出:**

```
86
```

**时间复杂度:** `O(NlogM)`，其中 `N` 是数组的大小，`M` 是数组中的最大个数。
**辅助空间:** `O(1)`