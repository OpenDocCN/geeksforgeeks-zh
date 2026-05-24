# 在线性时间内 k 次运算中最大化数组最右边的元素

> 原文: [https://www.geeksforgeeks.org/maximize-rightmost-array-element-by-decreasing-an-element-and-increasing-next-one-by-p-in-at-most-k-operations/](https://www.geeksforgeeks.org/maximize-rightmost-array-element-by-decreasing-an-element-and-increasing-next-one-by-p-in-at-most-k-operations/)

## 问题描述

给定一个大小为 `N` 的数组 `arr[]` 和一个整数 `p`，任务是找到数组 `arr[]` 最右边元素的最大可能值，最多执行 `k` 次运算。一次操作中，将 `arr[i]` 减少 `p`，将 `arr[i+1]` 增加 `p`。

## 示例

**输入:** `N = 4`，`p = 2`，`k = 5`，`arr = {3, 8, 1, 4}`
**输出:** `8`
**解释:**
可以执行以下操作来实现最右边元素的最大值:
1. 将 `arr[2]` 减少 2，将 `arr[3]` 增加 2，`arr = {3, 6, 3, 4}`
2. 将 `arr[2]` 减少 2，将 `arr[3]` 增加 2，`arr = {3, 4, 5, 4}`
3. 将 `arr[2]` 减少 2，将 `arr[3]` 增加 2，`arr = {3, 2, 5, 4}`
4. 将 `arr[3]` 减少 2，将 `arr[4]` 增加 2，`arr = {3, 2, 3, 6}`
5. 将 `arr[3]` 减少 2，将 `arr[4]` 增加 2，`arr = {3, 2, 1, 8}`
因此，最右边元素的最大可能值是 8。

**输入:** `N = 5`，`p = 1`，`k = 2`，`arr = {1, 2, 3, 4, 5}`
**输出:** `7`

## 朴素法

这个问题可以用[贪婪法](https://www.geeksforgeeks.org/greedy-algorithms/)天真地解决。按照以下步骤解决问题:
*   在 `while` 循环的同时运行，直到 `k` 大于 0。
*   在 `for` 内循环运行，在范围 `[N-2, 0]` 内循环 `i`。
*   检查 `arr[i]` 是否大于等于 `p`，将 `arr[i+1]` 增加 `p`，将 `arr[i]` 减少 `p` 并 `break` 回路。
*   将 `k` 的值减 1。
*   打印 `arr[N-1]`。

下面是上述方法的实现:

### C++

```cpp
// C++ program for above approach
#include <iostream>
using namespace std;

// Function to calculate maximum value of
// Rightmost element
void maxRightmostElement(int N, int k, int p, int arr[]){

     // Calculating maximum value of
     // Rightmost element
     while(k)
         {

          for(int i=N-2;i>=0;i--)
              {

                // Checking if arr[i] is operationable
                if(arr[i]>= p)
                  {
                      // Performing operation of i-th element
                      arr[i]=arr[i]-p;

                      arr[i+1]=arr[i+1]+p;

                      break;

                  } 

              }

         // Decreasing the value of k by 1
         k--;
        }

        // Printing rightmost element
        cout<<arr[N-1]<<endl;
}

// Driver Code
int main() {

    // Given Input
    int N = 4, p = 2, k = 5, arr[] = {3, 8, 1, 4};

    // Function Call
    maxRightmostElement(N, k, p, arr);
    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
class GFG {

    // Function to calculate maximum value of
    // Rightmost element
    static int maxRightmostElement(int N, int k, int p,
                                   int arr[])
    {

        // Calculating maximum value of
        // Rightmost element
        while (k > 0) {

            for (int i = N - 2; i >= 0; i--) {

                // Checking if arr[i] is operationable
                if (arr[i] >= p)
                {

                    // Performing operation of i-th element
                    arr[i] = arr[i] - p;

                    arr[i + 1] = arr[i + 1] + p;

                    break;
                }
            }

            // Decreasing the value of k by 1
            k--;
        }

        // returning the rightmost element
        return arr[N - 1];
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Given Input
        int N = 4, k = 5, p = 2;
        int arr[] = { 3, 8, 1, 4 };

        // Function Call
        System.out.println(
            maxRightmostElement(N, k, p, arr));
    }
}

// This code is contributed by dwivediyash
```

### Python 3

```python
# Python program for the above approach

# Function to calculate maximum value of
# Rightmost element
def maxRightmostElement(N, k, p, arr):

    # Calculating maximum value of
    # Rightmost element
    while(k) :

        for i in range(N - 2, -1, -1) :

            # Checking if arr[i] is operationable
            if(arr[i] >= p) :

                # Performing operation of i-th element
                arr[i] = arr[i] - p

                arr[i + 1] = arr[i + 1] + p

                break

        # Decreasing the value of k by 1
        k = k - 1

    # Printing rightmost element
    print(arr[N-1])

# Driver Code

# Given Input
N = 4
p = 2
k = 5
arr = [3, 8, 1, 4]

# Function Call
maxRightmostElement(N, k, p, arr)

# This code is contributed by sanjoy_62.
```

### C#

```csharp
using System;

public class GFG {

    // Function to calculate maximum value of
    // Rightmost element
    static int maxRightmostElement(int N, int k, int p,
                                   int []arr)
    {

        // Calculating maximum value of
        // Rightmost element
        while (k > 0) {

            for (int i = N - 2; i >= 0; i--) {

                // Checking if arr[i] is operationable
                if (arr[i] >= p) {

                    // Performing operation of i-th element
                    arr[i] = arr[i] - p;

                    arr[i + 1] = arr[i + 1] + p;

                    break;
                }
            }

            // Decreasing the value of k by 1
            k--;
        }

        // returning the rightmost element
        return arr[N - 1];
    }

    // Driver Code
    static public void Main()
    {

        // Given Input
        int N = 4, k = 5, p = 2;
        int[] arr = { 3, 8, 1, 4 };

        // Function Call
        Console.WriteLine(
            maxRightmostElement(N, k, p, arr));
    }
}

// This code is contributed by maddler.
```

### JavaScript

```javascript
// JavaScript Program to implement
// the above approach

// Function to calculate maximum value of
// Rightmost element
function maxRightmostElement(N, k, p, arr) {

    // Calculating maximum value of
    // Rightmost element
    while (k) {

        for (let i = N - 2; i >= 0; i--) {

            // Checking if arr[i] is operationable
            if (arr[i] >= p) {
                // Performing operation of i-th element
                arr[i] = arr[i] - p;

                arr[i + 1] = arr[i + 1] + p;

                break;

            }

        }

        // Decreasing the value of k by 1
        k--;
    }

    // Printing rightmost element
    document.write(arr[N - 1] + "<br>");
}

// Driver Code

// Given Input
let N = 4, p = 2, k = 5, arr = [3, 8, 1, 4];

// Function Call
maxRightmostElement(N, k, p, arr);

// This code is contributed by Potta Lokesh
```

**输出**

**时间复杂度:** `O(N * k)`
**辅助空间:** `O(1)`

## 优化法

上述方法可以通过观察以下事实进行优化: 数组的第 `i` 个元素 `arr[]` 可以在 `N-1-i` 次运算中为元素 `arr[N-1]` 贡献 `2`。按照以下步骤解决问题:
*   迭代一个循环，对于范围 `[N-2, 0]` 中的 `i`。
*   将 `ans` 初始化为 `arr[N-1]` 以存储最右边元素的最大值。
*   求第 `i` 元素的最小贡献，如 `d`，`d = min(arr[i]/2, k/(N-1-i))`。
*   将 `k` 减少 `d*(N-1-i)`，将 `ans` 增加 `d*2`。
*   打印 `ans`，将是最后一步。

### C++

```cpp
// C++ program for above approach
#include <iostream>
using namespace std;

// Function to calculate maximum value of
// Rightmost element
void maxRightmostElement(int N, int k, int arr[]){

     // Initializing ans to store
     // Maximum valued rightmost element
     int ans = arr[N-1];

     // Calculating maximum value of
     // Rightmost element
     for(int i=N-2; i>=0; i--)
       {
        int d = min(arr[i]/2, k/(N-1-i));

        k-=d*(N-1-i);

        ans+=d*2;
        }

        // Printing rightmost element
        cout<<ans<<endl;
}

// Driver Code
int main() {

    // Given Input
    int N = 4, k = 5, arr[] = {3, 8, 1, 4};

    // Function Call
    maxRightmostElement(N, k, arr);
    return 0;
}
```

## Java 语言

```java
// Java program for the above approach
import java.io.*;
class GFG {

  // Function to calculate maximum value of
  // Rightmost element
  static int maxRightmostElement(int N, int k, int p, int arr[])
  {

    // Initializing ans to store
    // Maximum valued rightmost element
    int ans = arr[N - 1];

    // Calculating maximum value of
    // Rightmost element
    for (int i = N - 2; i >= 0; i--) {
      int d = Math.min(arr[i] / p, k / (N - 1 - i));

      k -= d * (N - 1 - i);

      ans += d * p;
    }

    // returning rightmost element
    return  ans;
  }

  // Driver Code
  public static void main(String[] args)
  {
    // Given Input
    int N = 4, k = 5, p = 2;
    int arr[] = { 3, 8, 1, 4 };
    // Function Call
    System.out.println(maxRightmostElement(N, k, p, arr));
  }
}

// This code is contributed by dwivediyash
```

## 蟒蛇 3

```python
# Python 3 program for above approach

# Function to calculate maximum value of
# Rightmost element
def maxRightmostElement(N, k, arr):

    # Initializing ans to store
    # Maximum valued rightmost element
    ans = arr[N-1]

     # Calculating maximum value of
     # Rightmost element
    i = N - 2
    while(i >= 0):
        d = min(arr[i]//2, k//(N-1-i))

        k -= d * (N - 1 - i)

        ans+=d*2

        # Printing rightmost element
        i -= 1
    print(ans,end = " ")

# Driver Code
if __name__ == '__main__':

    # Given Input
    N = 4
    k = 5
    arr = [3, 8, 1, 4]

    # Function Call
    maxRightmostElement(N, k, arr)

    # This code is contributed by SURENDRA_GANGWAR.
```

## C\#

```csharp
// C# program for the above approach
using System;

public class GFG {

  // Function to calculate maximum value of
  // Rightmost element
  static int maxRightmostElement(int N, int k, int p, int []arr)
  {

    // Initializing ans to store
    // Maximum valued rightmost element
    int ans = arr[N - 1];

    // Calculating maximum value of
    // Rightmost element
    for (int i = N - 2; i >= 0; i--) {
      int d = Math.Min(arr[i] / p, k / (N - 1 - i));

      k -= d * (N - 1 - i);

      ans += d * p;
    }

    // returning rightmost element
    return  ans;
  }

  // Driver Code
  public static void Main(string[] args)
  {

    // Given Input
    int N = 4, k = 5, p = 2;
    int []arr = { 3, 8, 1, 4 };

    // Function Call
    Console.WriteLine(maxRightmostElement(N, k, p, arr));
  }
}

// This code is contributed by AnkThon
```

## Java 描述语言

```javascript
// JavaScript program for the above approach

  // Function to calculate maximum value of
  // Rightmost element
  function maxRightmostElement( N,  k,  p,  arr)
  {

    // Initializing ans to store
    // Maximum valued rightmost element
    var ans = arr[N - 1];

    // Calculating maximum value of
    // Rightmost element
    for (var i = N - 2; i >= 0; i--) {
      var d = Math.min(arr[i] / p, k / (N - 1 - i));

      k -= d * (N - 1 - i);

      ans += d * p;
    }

    // returning rightmost element
    return  ans;
  }

  // Driver Code
    // Given Input
    var N = 4, k = 3.5, p = 2;
    var arr = [ 3, 8, 1, 4 ];
    // Function Call
    document.write(maxRightmostElement(N, k, p, arr));

// This code is contributed by shivanisinghss2110
```

**输出**

```

```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`