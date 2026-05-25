# 通过给定的操作将数组简化为单个元素

> 原文：[https://www.geeksforgeeks.org/reduce-the-array-to-a-single-element-with-the-given-operation/](https://www.geeksforgeeks.org/reduce-the-array-to-a-single-element-with-the-given-operation/)

给定一个整数 `N` 和一个以排序方式包含从 `1` 到 `N` 的整数的数组。任务是通过执行以下操作将数组缩减为单个元素：
单次操作后，奇数位置的所有元素都将被移除。此操作将一直执行，直到数组中只剩下一个元素，并在最后打印该元素。

**示例：**

> **输入：** `N = 3`
> **输出：** `2`
> 最初数组将是 `arr[] = {1, 2, 3}`
> 第一次操作后，“1”和“3”将被移除，数组变成 `arr[] = {2}`
> 所以 `2` 是最后剩下的唯一元素。
>
> **输入：** `N = 6`
> **输出：** `4`
> `arr[] = {1, 2, 3, 4, 5, 6}`
> 第一次迭代后，数组变成 `{2, 4, 6}`
> 第二次迭代后，数组变成 `{4}`
> 所以 `4` 是最后一个元素。

**进场：** 对于这类问题：

*   编写多个测试用例和各自的输出。
*   分析给定输入的输出以及它们之间的关系。
*   一旦我们找到了关系，如果可能的话，我们将尝试用数学表达式的形式来表达它。
*   为上面的表达式编写代码/算法。

因此，让我们为给定的输入 `N` 及其相应的输出创建一个表。

| 输入(N) | 输出 |
| --- | --- |
| 3 | 2 |
| 4 | 4 |
| 6 | 4 |
| 8 | 8 |
| 12 | 8 |
| 20 | 16 |
|   |   |

**分析关系：** 输出是小于或等于 `N` 的最大的 `2` 的幂。使用上表，我们可以为输入范围创建输出表。

| 输入(N) | 输出 |
| --- | --- |
| 2-3 | 2 |
| 4-7 | 4 |
| 8-15 | 8 |
| 16-31 | 16 |
| 32-63 | 32 |
| 2<sup>i</sup> – 2<sup>i+1</sup>-1 | 2<sup>i</sup> |

下面是上述方法的实现：

## C++

```cpp
// C++ implementation of the approach

#include<bits/stdc++.h>
using namespace std;

// Function to return the final element
long getFinalElement(long n)
{
    long finalNum;
    for (finalNum = 2; finalNum * 2 <= n; finalNum *= 2)
            ;
    return finalNum;
}

// Driver code
int main()
{
       int N = 12;
    cout << getFinalElement(N) ;

   return 0;
}
// This code is contributed by Ryuga
```

## Java

```java
// Java implementation of the approach
class OddPosition {

    // Function to return the final element
    public static long getFinalElement(long n)
    {
        long finalNum;
        for (finalNum = 2; finalNum * 2 <= n; finalNum *= 2)
            ;
        return finalNum;
    }

    // Driver code
    public static void main(String[] args)
    {
        int N = 12;
        System.out.println(getFinalElement(N));
    }
}
```

## Python 3

```python
# Python 3 implementation of the approach

# Function to return the final element
def getFinalElement(n):

    finalNum = 2
    while finalNum * 2 <= n:
        finalNum *= 2
    return finalNum

# Driver code
if __name__ =="__main__":

    N = 12
    print( getFinalElement(N))

# This code is contributed
# by ChitraNayal
```

## C#

```csharp
// C# implementation of the approach
using System;

public class GFG{

    // Function to return the final element
    public static long getFinalElement(long n)
    {
        long finalNum;
        for (finalNum = 2; finalNum * 2 <= n; finalNum *= 2)
            ;
        return finalNum;
    }

    // Driver code
    static public void Main (){
        int N = 12;
        Console.WriteLine(getFinalElement(N));
    }
}
```

## PHP

```php
<?php
//PHP implementation of the approach

// Function to return the final element
function  getFinalElement($n)
{
    $finalNum=0;
    for ($finalNum = 2; ($finalNum * 2) <= $n; $finalNum *= 2) ;

    return $finalNum;
}

// Driver code
    $N = 12;
    echo  getFinalElement($N) ;

// This code is contributed by akt_mit
?>
```

## JavaScript

```javascript
<script>
// Javascript implementation of the approach

    // Function to return the final element
    function getFinalElement(n)
    {
        let finalNum;
        for (finalNum = 2; finalNum * 2 <= n; finalNum *= 2)
            ;
        return finalNum;
    }

    // Driver code
    let N = 12;
    document.write(getFinalElement(N));

// This code is contributed by avanitrachhadiya2155
</script>
```

**输出：**

```
8
```

**时间复杂度：** `O(logN)`
**辅助空间：** `O(1)`