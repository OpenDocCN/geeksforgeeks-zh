# 每次查询后求数组的和

> 原文: [https://www.geeksforgeeks.org/find-the-sum-of-array-after-performing-every-query/](https://www.geeksforgeeks.org/find-the-sum-of-array-after-performing-every-query/)

## 问题描述

给定大小为 `N` 和 `Q` 个查询的数组 `arr[]`，其中每个查询包含两个整数 `X` 和 `Y`，任务是在执行每个 `Q` 查询后找到数组的和，使得对于每个查询，数组 `arr[]` 中值为 `X` 的元素被更新为 `Y`。

## 示例

**输入:** `arr[] = {1, 2, 3, 4}`，`Q = {(1, 2), (3, 4), (2, 4)}`
**输出:** `11 12 16`
**解释:**
第 1 次运算是用 2 代替每 1，所以数组变成 `arr[] = {2, 2, 3, 4}`，`ans sum = 11`。
第 2 次运算是用 4 代替每 3，所以数组变成 `arr[] = {2, 2, 4, 4}`，`ans sum = 12`。
第 3 次运算是用 4 代替每 2，所以数组变成 `arr[] = {4, 4, 4, 4}`，`ans sum = 16`。

**输入:** `arr[] = {1}`，`Q = {(1, 2)}`
**输出:** `2`

## 方法

### 天真方法

天真方法是遍历每个查询，并为每个查询通过遍历数组用值 `X` 到 `Y` 更新数组 `arr[]` 中的每个元素。每次查询后打印 `arr[]` 中所有元素的总和。
**时间复杂度:** `O(N*Q)`
**辅助空间:** `O(1)`

### 高效方法

为了优化上述方法，思路是计算数组中所有元素的和（比如说 `sum`）`arr[]` 并将所有元素的频率存储在无序_map（比如说 `M`）中。对于每个查询 `(X, Y)` 执行以下操作:

1.  从无序_map `M` 中找到 `X` 的频率。
2.  减去 `X * M[X]` 的总和，不包括 `X` 的总和。
3.  将总和增加 `Y * M[X]`，不包括 `Y` 的总和。
4.  将地图中 `Y` 的频率增加 `M[X]`。
5.  最后打印总和，从地图 `M` 中去掉 `X`。

下面是上述方法的实现。

## C++14

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function that solves the given queries
void solve(int ar[], int n, int b[],
           int c[], int q)
{
    // This map will store the
    // frequency of each element
    unordered_map<int, int> mp;

    // sum stores the sum of
    // all elements of array
    int sum = 0;

    for (int x = 0; x < n; x++) {
        sum += ar[x];
        mp[ar[x]]++;
    }

    // Process the queries
    for (int x = 0; x < q; x++) {

        // Find occurrence of
        // b[x] from map
        int occur1 = mp[b[x]];

        // Decrease sum
        sum = sum - occur1 * b[x];

        // Erase b[x] from map
        mp.erase(b[x]);

        // Increase sum
        sum = sum + occur1 * c[x];

        // Increase frequency
        // of c[x] in map
        mp[c[x]] += occur1;

        // Print sum
        cout << sum << " ";
    }
}

// Driver Code
int main()
{
    // Given arr[]
    int ar[] = { 1, 2, 3, 4 };
    int n = 4;

    // Given Queries
    int q = 3;
    int b[] = { 1, 3, 2 };
    int c[] = { 2, 4, 4 };

    // Function Call
    solve(ar, n, b, c, q);
    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function that solves the given queries
static void solve(int ar[], int n, int b[],
                   int c[], int q)
{

    // This map will store the
    // frequency of each element
    Map<Integer, Integer> mp = new HashMap<>();

    // sum stores the sum of
    // all elements of array
    int sum = 0;

    for(int x = 0; x < n; x++)
    {
        sum += ar[x];
        mp.put(ar[x], mp.getOrDefault(ar[x], 0) + 1);
    }

    // Process the queries
    for(int x = 0; x < q; x++)
    {

        // Find occurrence of
        // b[x] from map
        int occur1 = mp.get(b[x]);

        // Decrease sum
        sum = sum - occur1 * b[x];

        // Erase b[x] from map
        mp.remove(b[x]);

        // Increase sum
        sum = sum + occur1 * c[x];

        // Increase frequency
        // of c[x] in map
        mp.put(c[x], mp.get(c[x]) + occur1);

        // Print sum
        System.out.print(sum + " ");
    }
}

// Driver Code
public static void main (String[] args)
{

    // Given arr[]
    int ar[] = { 1, 2, 3, 4 };
    int n = 4;

    // Given queries
    int q = 3;
    int b[] = { 1, 3, 2 };
    int c[] = { 2, 4, 4 };

    // Function call
    solve(ar, n, b, c, q);
}
}

// This code is contributed by offbeat
```

## Python3

```python
# Python3 program for the above approach

# Function that solves the given queries
def solve(ar, n, b, c, q):

    # This map will store the
    # frequency of each element
    mp = {}

    # sum stores the sum of
    # all elements of array
    sum = 0

    for x in range(n):
        sum += ar[x]
        mp[ar[x]] = mp.get(ar[x], 0) + 1

    # Process the queries
    for x in range(q):

        # Find occurrence of
        # b[x] from map
        occur1 = mp[b[x]]

        # Decrease sum
        sum = sum - occur1 * b[x]

        # Erase b[x] from map
        del mp[b[x]]

        # Increase sum
        sum = sum + occur1 * c[x]

        # Increase frequency
        # of c[x] in map
        mp[c[x]] += occur1

        # Print sum
        print(sum, end = " ")

# Driver Code
if __name__ == '__main__':

    # Given arr[]
    ar = [ 1, 2, 3, 4 ]
    n = 4

    # Given Queries
    q = 3
    b = [ 1, 3, 2 ]
    c = [ 2, 4, 4 ]

    # Function Call
    solve(ar, n, b, c, q)

# This code is contributed by mohit kumar 29
```

## C#

```csharp
// C# program for
// the above approach
using System;
using System.Collections.Generic;
class GFG{

// Function that solves
// the given queries
static void solve(int []ar, int n,
                  int []b, int []c,
                  int q)
{   
  // This map will store the
  // frequency of each element
  Dictionary<int,
             int> mp = new Dictionary<int,
                                      int>();

  // sum stores the sum of
  // all elements of array
  int sum = 0;

  for(int x = 0; x < n; x++)
  {
    sum += ar[x];
    if(mp.ContainsKey(ar[x]))
      mp[ar[x]] = mp[ar[x]] + 1;
    else
      mp.Add(ar[x], 1);
  }

  // Process the queries
  for(int x = 0; x < q; x++)
  {
    // Find occurrence of
    // b[x] from map
    int occur1 = mp[b[x]];

    // Decrease sum
    sum = sum - occur1 * b[x];

    // Erase b[x] from map
    mp.Remove(b[x]);

    // Increase sum
    sum = sum + occur1 * c[x];

    // Increase frequency
    // of c[x] in map
    if(mp.ContainsKey(c[x]))
      mp[c[x]] = mp[c[x]] + occur1;

    // Print sum
    Console.Write(sum + " ");
  }
}

// Driver Code
public static void Main(String[] args)
{   
  // Given []arr
  int []ar = {1, 2, 3, 4};
  int n = 4;

  // Given queries
  int q = 3;
  int []b = {1, 3, 2};
  int []c = {2, 4, 4};

  // Function call
  solve(ar, n, b, c, q);
}
}

// This code is contributed by Princi Singh
```

## JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function that solves the given queries
function solve(ar, n, b, c, q)
{
    // This map will store the
    // frequency of each element
    var mp = new Map();

    // sum stores the sum of
    // all elements of array
    var sum = 0;

    for (var x = 0; x < n; x++) {
        sum += ar[x];
        if(mp.has(ar[x]))
            mp.set(ar[x], mp.get(ar[x])+1)
        else
            mp.set(ar[x], 1);
    }

    // Process the queries
    for (var x = 0; x < q; x++) {

        // Find occurrence of
        // b[x] from map
        var occur1 = mp.get(b[x]);

        // Decrease sum
        sum = sum - occur1 * b[x];

        // Erase b[x] from map
        mp.set(b[x], 0);

        // Increase sum
        sum = sum + occur1 * c[x];

        // Increase frequency
        // of c[x] in map
        if(mp.has(c[x]))
            mp.set(c[x], mp.get(c[x])+occur1)
        else
            mp.set(c[x], occur1);

        // Print sum
        document.write( sum + " ");
    }
}

// Driver Code
// Given arr[]
var ar = [1, 2, 3, 4];
var n = 4;
// Given Queries
var q = 3;
var b = [1, 3, 2];
var c = [2, 4, 4];
// Function Call
solve(ar, n, b, c, q);

</script>
```

**输出:**

```
11 12 16
```

**时间复杂度:** `O(N+Q)`
**辅助空间:** `O(N)`