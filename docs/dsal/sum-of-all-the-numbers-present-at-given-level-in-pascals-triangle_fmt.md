# 帕斯卡三角形中给定级别的所有数字的总和

> 原文: [https://www.geeksforgeeks.org/sum-of-all-the-numbers-present-at-given-level-in-pascals-triangle/](https://www.geeksforgeeks.org/sum-of-all-the-numbers-present-at-given-level-in-pascals-triangle/)

给定一个 `L` 级，任务是求帕斯卡三角形中给定级上所有整数的和。
一个 6 级帕斯卡三角形如下所示:

> 1
> 1 1
> 1 2 1
> 1 3 3 1
> 1 4 6 4 1
> 1 5 10 10 5 1

`例:`

> `输入:` `L = 3`
> `输出:` 4
> 1 + 2 + 1 = 4
> `输入:` `L = 2`
> `输出:` 2

`进场:` 如果我们仔细观察，级数的总和会像 **1、2、4、8、16……** 一样继续下去，这是一个 `a = 1`，`r = 2` 的 GP 系列。
因此，`L`th 水平的和是上述系列中的第 `L` 项。

```
Lth term = 2^(L-1)
```

以下是上述方法的实现:

## C++

```cpp
// C++ implementation of the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find sum of numbers at
// Lth level in Pascals Triangle
int sum(int h)
{
    return pow(2, h - 1);
}

// Driver Code
int main()
{
    int L = 3;

    cout << sum(L);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG
{

    // Function to find sum of numbers at
    // Lth level in Pascals Triangle
    static int sum(int h)
    {
        return (int)Math.pow(2, h - 1);
    }

    // Driver Code
    public static void main (String[] args)
    {
        int L = 3;

        System.out.println(sum(L));
    }
}

// This code is contributed by AnkitRai01
```

## Python 3

```python
# Python3 implementation of the above approach

# Function to find sum of numbers at
# Lth level in Pascals Triangle
def summ(h):
    return pow(2, h - 1)

# Driver Code
L = 3

print(summ(L))

# This code is contributed by mohit kumar
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

    // Function to find sum of numbers at
    // Lth level in Pascals Triangle
    static int sum(int h)
    {
        return (int)Math.Pow(2, h - 1);
    }

    // Driver Code
    public static void Main ()
    {
        int L = 3;

        Console.WriteLine(sum(L));
    }
}

// This code is contributed by anuj_67..
```

## JavaScript

```javascript
<script>

// Javascript implementation of the above approach

// Function to find sum of numbers at
// Lth level in Pascals Triangle
function sum(h)
{
    return Math.pow(2, h - 1);
}

// Driver Code
var L = 3;

document.write(sum(L));

</script>
```

**Output:**

```
4
```

**时间复杂度:** `O(1)`