# 最慢的排序算法

> 原文：[https://www.geeksforgeeks.org/the-slowest-sorting-algorithms/](https://www.geeksforgeeks.org/the-slowest-sorting-algorithms/)

一种[排序算法](https://www.geeksforgeeks.org/sorting-algorithms/)用于根据元素上的比较运算符重新排列给定的数组或列表元素。比较运算符用于确定元素在相应的[数据结构](https://www.geeksforgeeks.org/data-structures/)中的新顺序。但是下面是一些最慢的排序算法：

## 走狗排序

[走狗排序](https://www.geeksforgeeks.org/stooge-sort/)是一种[递归](https://www.geeksforgeeks.org/recursion/)排序算法。它递归地对数组进行部分划分和排序。以下是排序的步骤：

*   如果索引`0`的值大于最后一个索引的值，则交换它们。
*   如果数组中的元素数量大于2：
    *   递归调用`stoogesort`函数对数组的前`2/3`元素进行排序。
    *   递归调用`stoogesort`函数对数组的后`2/3`元素进行排序。
    *   再次递归调用`stoogesort`函数对前`2/3`元素进行排序，以确认结果数组是否已排序。
*   打印排序后的数组。

下面是上述方法的实现：

### C++

```cpp
// C++ program for the stooge sort
#include <iostream>
using namespace std;

// Function to implement stooge sort
void stoogesort(int arr[], int l, int h)
{
    // Base Case
    if (l >= h)
        return;

    // If first element is smaller than
    // last element, swap them
    if (arr[l] > arr[h])
        swap(arr[l], arr[h]);

    // If there are more than 2 elements
    // in the array
    if (h - l + 1 > 2) {
        int t = (h - l + 1) / 3;

        // Recursively sort the first
        // 2/3 elements
        stoogesort(arr, l, h - t);

        // Recursively sort the last
        // 2/3 elements
        stoogesort(arr, l + t, h);

        // Recursively sort the first
        // 2/3 elements again
        stoogesort(arr, l, h - t);
    }
}

// Driver Code
int main()
{
    int arr[] = { 2, 4, 5, 3, 1 };
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    stoogesort(arr, 0, N - 1);

    // Display the sorted array
    for (int i = 0; i < N; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```

### Java

```java
// Java program for the
// stooge sort
class GFG{

// Function to implement
// stooge sort
static void stoogesort(int arr[],
                       int l, int h)
{
  // Base Case
  if (l >= h)
    return;

  // If first element is smaller
  // than last element, swap them
  if (arr[l] > arr[h])
  {
    int temp = arr[l];
    arr[l] = arr[h];
    arr[h] = temp;
  }

  // If there are more than
  // 2 elements in the array
  if (h - l + 1 > 2)
  {
    int t = (h - l + 1) / 3;

    // Recursively sort the
    // first 2/3 elements
    stoogesort(arr, l, h - t);

    // Recursively sort the
    // last 2/3 elements
    stoogesort(arr, l + t, h);

    // Recursively sort the
    // first 2/3 elements again
    stoogesort(arr, l, h - t);
  }
}

// Driver Code
public static void main(String[] args)
{
  int arr[] = {2, 4, 5, 3, 1};
  int N = arr.length;

  // Function Call
  stoogesort(arr, 0, N - 1);

  // Display the sorted array
  for (int i = 0; i < N; i++)
  {
    System.out.print(arr[i] + " ");
  }
}
}

// This code is contributed by Chitranayal
```

### Python 3

```python
# Python3 program for the stooge sort

# Function to implement stooge sort
def stoogesort(arr, l, h):

    # Base Case
    if (l >= h):
        return

    # If first element is smaller than
    # last element, swap them
    if (arr[l] > arr[h]):
        temp = arr[l]
        arr[l] = arr[h]
        arr[h] = temp

    # If there are more than 2 elements
    # in the array
    if (h - l + 1 > 2):
        t = (h - l + 1) // 3

        # Recursively sort the first
        # 2/3 elements
        stoogesort(arr, l, h - t)

        # Recursively sort the last
        # 2/3 elements
        stoogesort(arr, l + t, h)

        # Recursively sort the first
        # 2/3 elements again
        stoogesort(arr, l, h - t)

# Driver Code
arr = [ 2, 4, 5, 3, 1 ]
N = len(arr)

# Function Call
stoogesort(arr, 0, N - 1)

# Display the sorted array
for i in range(N):
    print(arr[i], end = " ")

# This code is contributed by code_hunt
```

### C#

```csharp
// C# program for the
// stooge sort
using System;

class GFG{

// Function to implement
// stooge sort
static void stoogesort(int []arr,
                       int l, int h)
{
    // Base Case
    if (l >= h)
        return;

    // If first element is smaller
    // than last element, swap them
    if (arr[l] > arr[h])
    {
        int temp = arr[l];
        arr[l] = arr[h];
        arr[h] = temp;
    }

    // If there are more than
    // 2 elements in the array
    if (h - l + 1 > 2)
    {
        int t = (h - l + 1) / 3;

        // Recursively sort the first
        // 2/3 elements
        stoogesort(arr, l, h - t);

        // Recursively sort the last
        // 2/3 elements
        stoogesort(arr, l + t, h);

        // Recursively sort the first
        // 2/3 elements again
        stoogesort(arr, l, h - t);
    }
}

// Driver Code
public static void Main(String[] args)
{
    int []arr = {2, 4, 5, 3, 1};
    int N = arr.Length;

    // Function Call
    stoogesort(arr, 0, N - 1);

    // Display the sorted array
    for (int i = 0; i < N; i++)
    {
        Console.Write(arr[i] + " ");
    }
}
}

// This code is contributed by PrinciRaj1992
```

### JavaScript

```javascript
<script>

// Javascript program for the
// stooge sort

// Function to implement
// stooge sort
function stoogesort(arr, l, h)
{

    // Base Case
    if (l >= h)
        return;

    // If first element is smaller
    // than last element, swap them
    if (arr[l] > arr[h])
    {
        let temp = arr[l];
        arr[l] = arr[h];
        arr[h] = temp;
    }

    // If there are more than
    // 2 elements in the array
    if (h - l + 1 > 2)
    {
        let t = Math.floor((h - l + 1) / 3);

        // Recursively sort the
        // first 2/3 elements
        stoogesort(arr, l, h - t);

        // Recursively sort the
        // last 2/3 elements
        stoogesort(arr, l + t, h);

        // Recursively sort the
        // first 2/3 elements again
        stoogesort(arr, l, h - t);
    }
}

// Driver Code
let arr = [ 2, 4, 5, 3, 1 ];
let N = arr.length;

// Function Call
stoogesort(arr, 0, N - 1);

// Display the sorted array
for (let i = 0; i < N; i++)
{
    document.write(arr[i] + " ");
}

// This code is contributed by avanitrachhadiya2155

</script>
```

**输出：**

```
1 2 3 4 5
```