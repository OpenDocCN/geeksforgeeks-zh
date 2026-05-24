# 给定数组中所有无序对的按位“或”

> 原文：[https://www.geeksforgeeks.org/bitwise-or-of-all-unordered-pairs-from-a-given-array/](https://www.geeksforgeeks.org/bitwise-or-of-all-unordered-pairs-from-a-given-array/)

给定一个大小为 `N` 的数组 `arr[]`，任务是从给定的数组中找到所有可能的无序对的位异或。

## 示例

> **输入**：`arr[] = {1, 5, 3, 7}`
> **输出**：`7`
> **解释**：
> 所有可能的无序对为 `(1, 5)`、`(1, 3)`、`(1, 7)`、`(5, 3)`、`(5, 7)`、`(3, 7)`
> 所有可能对的按位 OR 为 `= {(1 | 5) | (1 | 3) | (1 | 7) | (5 | 3) | (5 | 7) | (3 | 7)}`
>
> **输入**：`arr[] = {4, 5, 12, 15}`
> **输出**：`15`

## 方法

解决这个问题最简单的方法是遍历数组和生成给定数组的所有可能的对。最后，打印给定数组的所有可能对的每个元素的位或。按照以下步骤解决问题：

*   初始化一个变量，比如 `totalOR`，来存储所有可能对的每个元素的位方式 OR。
*   遍历给定数组，从给定数组中生成所有可能的对 `(arr[i], arr[j])`，对于每个对 `(arr[i], arr[j])`，更新 `totalOR = (totalOR | arr[i] | arr[j])` 的值。
*   最后，打印 `totalOR` 的值。

下面是上述方法的实现：

### C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the Bitwise OR of
// all possible pairs from the array
int TotalBitwiseORPair(int arr[], int N)
{

    // Stores bitwise OR of all
    // possible pairs from arr[]
    int totalOR = 0;

    // Traverse the array and calculate
    // bitwise OR of all possible pairs
    for (int i = 0; i < N; i++) {
        for (int j = i + 1; j < N;
             j++) {

            // Update totalOR
            totalOR |= (arr[i] | arr[j]);
        }
    }

    // Return Bitwise OR of all
    // possible pairs from arr[]
    return totalOR;
}

// Driver Code
int main()
{
    int arr[] = { 4, 5, 12, 15 };
    int N = sizeof(arr) / sizeof(arr[0]);
    cout << TotalBitwiseORPair(arr, N);
}
```

### Java

```java
// Java program to implement
// the above approach
import java.util.*;
class GFG{

// Function to find the Bitwise OR of
// all possible pairs from the array
static int TotalBitwiseORPair(int arr[],
                              int N)
{
  // Stores bitwise OR of all
  // possible pairs from arr[]
  int totalOR = 0;

  // Traverse the array and
  // calculate bitwise OR of
  // all possible pairs
  for (int i = 0; i < N; i++)
  {
    for (int j = i + 1; j < N;
         j++)
    {
      // Update totalOR
      totalOR |= (arr[i] |
                  arr[j]);
    }
  }

  // Return Bitwise OR of all
  // possible pairs from arr[]
  return totalOR;
}

// Driver Code
public static void main(String[] args)
{
  int arr[] = {4, 5, 12, 15};
  int N = arr.length;
  System.out.print(TotalBitwiseORPair(arr, N));
}
}

// This code is contributed by sanjoy_62
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to find the Bitwise
# OR of all possible pairs
# from the array
def TotalBitwiseORPair(arr, N):

    # Stores bitwise OR of all
    # possible pairs from arr[]
    totalOR = 0

    # Traverse the array and
    # calculate bitwise OR of
    # all possible pairs
    for i in range(N):
        for j in range(i + 1, N):

            # Update totalOR
            totalOR |= (arr[i] | arr[j])

    # Return Bitwise OR of all
    # possible pairs from arr[]
    return totalOR

# Driver Code
if __name__ == '__main__':

    arr = [4, 5, 12, 15]
    N = len(arr)
    print(TotalBitwiseORPair(arr, N))

# This code is contributed by Mohit Kumar 29
```

### C#

```csharp
// C# program to implement
// the above approach
using System;

class GFG{

// Function to find the Bitwise OR of
// all possible pairs from the array
static int TotalBitwiseORPair(int[] arr,
                              int N)
{

  // Stores bitwise OR of all
  // possible pairs from arr[]
  int totalOR = 0;

  // Traverse the array and
  // calculate bitwise OR of
  // all possible pairs
  for(int i = 0; i < N; i++)
  {
    for(int j = i + 1; j < N; j++)
    {

      // Update totalOR
      totalOR |= (arr[i] | arr[j]);
    }
  }

  // Return Bitwise OR of all
  // possible pairs from arr[]
  return totalOR;
}

// Driver Code
public static void Main()
{
    int[] arr = { 4, 5, 12, 15 };
    int N = arr.Length;

    Console.WriteLine(TotalBitwiseORPair(arr, N));
}
}

// This code is contributed by susmitakundugoaldanga
```

### JavaScript

```javascript
<script>

// JavaScript program to implement
// the above approach

// Function to find the Bitwise OR of
// all possible pairs from the array
function TotalBitwiseORPair(arr, N)
{

    // Stores bitwise OR of all
    // possible pairs from arr[]
    let totalOR = 0;

    // Traverse the array and calculate
    // bitwise OR of all possible pairs
    for (let i = 0; i < N; i++) {
        for (let j = i + 1; j < N;
            j++) {

            // Update totalOR
            totalOR |= (arr[i] | arr[j]);
        }
    }

    // Return Bitwise OR of all
    // possible pairs from arr[]
    return totalOR;
}

// Driver Code

    let arr = [ 4, 5, 12, 15 ];
    let N = arr.length;
    document.write(TotalBitwiseORPair(arr, N));

// This code is contributed by Surbhi Tyagi

</script>
```

**输出**：

```
15
```

**时间复杂度**：`O(N^2)`
**辅助空间**：`O(1)`

## 高效方法

为了优化上述方法，该想法基于以下观察：

> `1 | 1 | 1 | ….. (n 次) = 1`
> `0 | 0 | 0 | ….. (n 次) = 0`
> 因此，`(a | a | a | ….. (n 次)) = a`

按照以下步骤解决问题：

*   初始化一个变量，比如 `totalOR` 来存储数组中所有可能的无序对的按位 OR。
*   遍历数组并更新 `totalOR = (totalOR | arr[i])` 的值。
*   最后，打印 `totalOR` 的值。

下面是上述方法的实现：

### C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the bitwise OR of
// all possible pairs of the array
int TotalBitwiseORPair(int arr[], int N)
{

    // Stores bitwise OR of all
    // possible pairs of arr[]
    int totalOR = 0;

    // Traverse the array arr[]
    for (int i = 0; i < N; i++) {

        // Update totalOR
        totalOR |= arr[i];
    }

    // Return bitwise OR of all
    // possible pairs of arr[]
    return totalOR;
}

// Driver Code
int main()
{
    int arr[] = { 4, 5, 12, 15 };
    int N = sizeof(arr) / sizeof(arr[0]);
    cout << TotalBitwiseORPair(arr, N);
}
```

### Java

```java
// Java program to implement
// the above approach
import java.util.*;

class GFG{

// Function to find the bitwise OR of
// all possible pairs of the array
static int TotalBitwiseORPair(int arr[],
                              int N)
{

    // Stores bitwise OR of all
    // possible pairs of arr[]
    int totalOR = 0;

    // Traverse the array arr[]
    for(int i = 0; i < N; i++)
    {

        // Update totalOR
        totalOR |= arr[i];
    }

    // Return bitwise OR of all
    // possible pairs of arr[]
    return totalOR;
}

// Driver Code
public static void main(String[] args)
{
    int arr[] = { 4, 5, 12, 15 };
    int N = arr.length;

    System.out.print(TotalBitwiseORPair(arr, N));
}
}

// This code is contributed by gauravrajput1
```

### Python 3

```python
# Python program to implement
# the above approach

# Function to find the bitwise OR of
# all possible pairs of the array
def TotalBitwiseORPair(arr, N):

    # Stores bitwise OR of all
    # possible pairs of arr
    totalOR = 0;

    # Traverse the array arr
    for i in range(N):

        # Update totalOR
        totalOR |= arr[i];

    # Return bitwise OR of all
    # possible pairs of arr
    return totalOR;

# Driver Code
if __name__ == '__main__':
    arr = [4, 5, 12, 15];
    N = len(arr);

    print(TotalBitwiseORPair(arr, N));

    # This code is contributed by shikhasingrajput
```

## C#

```
// C# program to implement
// the above approach
using System;

class GFG{

// Function to find the bitwise OR of
// all possible pairs of the array
static int TotalBitwiseORPair(int []arr,
                              int N)
{

    // Stores bitwise OR of all
    // possible pairs of []arr
    int totalOR = 0;

    // Traverse the array []arr
    for(int i = 0; i < N; i++)
    {

        // Update totalOR
        totalOR |= arr[i];
    }

    // Return bitwise OR of all
    // possible pairs of []arr
    return totalOR;
}

// Driver Code
public static void Main(String[] args)
{
    int []arr = { 4, 5, 12, 15 };
    int N = arr.Length;

    Console.Write(TotalBitwiseORPair(arr, N));
}
}

// This code is contributed by Princi Singh
```

## java 描述语言

```
<script>

// JavaScript program to implement
// the above approach

// Function to find the bitwise OR of
// all possible pairs of the array
function TotalBitwiseORPair(arr, N)
{

    // Stores bitwise OR of all
    // possible pairs of arr[]
    let totalOR = 0;

    // Traverse the array arr[]
    for(let i = 0; i < N; i++)
    {

        // Update totalOR
        totalOR |= arr[i];
    }

    // Return bitwise OR of all
    // possible pairs of arr[]
    return totalOR;
}

// Driver Code

    let arr = [ 4, 5, 12, 15 ];
    let N = arr.length;

    document.write(TotalBitwiseORPair(arr, N));

</script>
```

`Output:`

```

```

`时间复杂度:` O(N)
`辅助空间:` O(1)