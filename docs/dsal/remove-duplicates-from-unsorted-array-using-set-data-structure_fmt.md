# 使用集合数据结构

从未排序的数组中删除重复项

> 原文: [https://www.geeksforgeeks.org/remove-duplicates-from-unsorted-array-using-set-data-structure/](https://www.geeksforgeeks.org/remove-duplicates-from-unsorted-array-using-set-data-structure/)

给定一个未排序的整数数组，在删除重复元素后打印该数组。我们需要根据第一次出现的情况打印不同的数组元素。

### 示例

```
Input: arr[] = { 1, 2, 5, 1, 7, 2, 4, 2}
Output: 1 2 5 7 4
Explanation: {1, 2} appear more than one time.

Input: arr[] = { 3, 3, 4, 1, 1}
Output: 3 4 1
```

### 方法

*   获取一个集合（例如 C++ 中的 `unordered_set` 或 Java 中的 `LinkedHashSet`）。
*   将所有数组元素插入集合中。集合不允许重复。`LinkedHashSet` 等集合会保留插入顺序，因此它会删除重复项，并按插入顺序打印元素。
*   将形成的集合转换回数组。
*   打印集合的元素。

下面是上述方法的实现：

## C++

```cpp
// CPP program to remove duplicates
// from unsorted array
#include <bits/stdc++.h>
using namespace std;

// Function to remove duplicate from array
void removeDuplicates(int arr[], int n)
{
    unordered_set<int> s;

    // adding elements to LinkedHashSet
    for (int i = 0; i < n; i++)
        s.insert(arr[i]);

    // Print the elements of LinkedHashSet
    cout << "[ ";
    for (auto x : s)
        cout << x << " ";
    cout << "]";
}

// Driver code
int main()
{
    int arr[] = { 1, 2, 5, 1, 7, 2, 4, 2 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // Function call
    removeDuplicates(arr, n);
}

// This code is contributed
// by Surendra_Gangwar
```

## Java

```java
// Java program to remove duplicates
// from unsorted array

import java.util.*;

class GFG {

    // Function to remove duplicate from array
    public static void removeDuplicates(int[] arr)
    {
        LinkedHashSet<Integer> set
            = new LinkedHashSet<Integer>();

        // adding elements to LinkedHashSet
        for (int i = 0; i < arr.length; i++)
            set.add(arr[i]);

        // Print the elements of LinkedHashSet
        System.out.print(set);
    }

    // Driver code
    public static void main(String[] args)
    {
        int arr[] = { 1, 2, 5, 1, 7, 2, 4, 2 };

        // Function call
        removeDuplicates(arr);
    }
}
```

## Python 3

```python
# Python3 program to remove duplicates
def removeDulipcates(arr):

    # convert the arr into set and then into list
    return list(set(arr))

# Driver Code
arr = [1, 2, 5, 1, 7, 2, 4, 2]

# Function call
print(removeDulipcates(arr))

# This code is contributed
# by Mohit Kumar
```

## C#

```csharp
// C# program to remove duplicates
// from unsorted array
using System;
using System.Collections.Generic;

class GFG
{
    // Function to remove duplicate from array
    public static void removeDuplicates(int[] arr)
    {
        HashSet<int> set = new HashSet<int>();

        // adding elements to LinkedHashSet
        for (int i = 0; i < arr.Length; i++)
            set.Add(arr[i]);

        // Print the elements of HashSet
        foreach(int item in set) Console.Write(item + ", ");
    }

    // Driver code
    public static void Main(String[] args)
    {
        int[] arr = { 1, 2, 5, 1, 7, 2, 4, 2 };

        // Function call
        removeDuplicates(arr);
    }
}

// This code is contributed by 29AjayKumar
```

## JavaScript

```javascript
<script>

// Javascript program to remove duplicates
// from unsorted array

// Function to remove duplicate from array
function removeDuplicates(arr)
{
    let set = new Set();

    // Adding elements to LinkedHashSet
    for(let i = 0; i < arr.length; i++)
        set.add(arr[i]);

    // Print the elements of LinkedHashSet
    document.write("[" + Array.from(set).join(", ") + "]");
}

 // Driver code
let arr = [ 1, 2, 5, 1, 7, 2, 4, 2 ];

// Function call
removeDuplicates(arr);

// This code is contributed by patel2127

</script>
```

## 输出

## 时间复杂度

`O(N)`