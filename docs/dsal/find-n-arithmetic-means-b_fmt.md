# 找出 A 和 B 之间的 N 个算术平均值

> 原文：[https://www.geeksforgeeks.org/find-n-arithmetic-means-b/](https://www.geeksforgeeks.org/find-n-arithmetic-means-b/)

给定三个整数 `A`、`B` 和 `N`，任务是找出 `A` 和 `B` 之间的 `N` 个算术平均值。我们基本上需要在[算术级数](https://www.geeksforgeeks.org/program-n-th-term-arithmetic-progression-series/)中插入 `N` 个项，其中 `A` 和 `B` 是第一项和最后一项。

示例：

```
Input : A = 20 B = 32 N = 5
Output : 22 24 26 28 30
The Arithmetic progression series as 
20 22 24 26 28 30 32 

Input : A = 5  B = 35  N = 5
Output : 10 15 20 25 30
```

**进场：**
让 `A1`，`A2`，`A3`，`A4`……`An` 为两个给定数字 `A` 和 `B` 之间的 `N` 个算术平均值，然后 `A`，`A1`，`A2`…..`An`，`B` 将处于算术级数。
现在 `B` 是算术级数的第 `(N+2)` 项。
所以：
求等差数列的第 `(N+2)` 项，其中 `d` 为公差

`B = A+(N+2–1)d`
`B–A =(N+1)d`

所以公差 `d` 由下式给出：

**`d =(B–A)/(N+1)`**

所以现在我们有了 `A` 的值和公共差 `d` 的值，现在我们可以找到 `A` 和 `B` 之间的所有 `N` 个算术平均值。

## C++

```cpp
// C++ program to find n arithmetic 
// means between A and B
#include <bits/stdc++.h>
using namespace std;

// Prints N arithmetic means between
// A and B.
void printAMeans(int A, int B, int N)
{
    // calculate common difference(d)
    float d = (float)(B - A) / (N + 1);

    // for finding N the arithmetic 
    // mean between A and B
    for (int i = 1; i <= N; i++) 
        cout << (A + i * d) <<" ";    
}

// Driver code to test above 
int main()
{
    int A = 20, B = 32, N = 5;
    printAMeans(A, B, N);    
    return 0;
}
```

## Java

```java
// java program to illustrate
// n arithmetic mean between 
// A and B
import java.io.*;
import java.lang.*;
import java.util.*;

public class GFG {

    // insert function for calculating the means
    static void printAMeans(int A, int B, int N)
    {       
        // Finding the value of d Common difference
        float d = (float)(B - A) / (N + 1);

        // for finding N the Arithmetic 
        // mean between A and B
        for (int i = 1; i <= N; i++) 
          System.out.print((A + i * d) + " ");

    }

    // Driver code
    public static void main(String args[])
    {
        int A = 20, B = 32, N = 5;
        printAMeans(A, B, N);
    }
}
```

## Python 3

```python
# Python3 program to find n arithmetic
# means between A and B

# Prints N arithmetic means 
# between A and B.
def printAMeans(A, B, N):

    # Calculate common difference(d)
    d = (B - A) / (N + 1)

    # For finding N the arithmetic 
    # mean between A and B
    for i in range(1, N + 1): 
        print(int(A + i * d), end = " ") 

# Driver code
A = 20; B = 32; N = 5
printAMeans(A, B, N) 

# This code is contributed by Smitha Dinesh Semwal
```

## C#

```csharp
// C# program to illustrate
// n arithmetic mean between 
// A and B
using System;

public class GFG {

    // insert function for calculating the means
    static void printAMeans(int A, int B, int N)
    {     
        // Finding the value of d Common difference
        float d = (float)(B - A) / (N + 1);

        // for finding N the Arithmetic 
        // mean between A and B
        for (int i = 1; i <= N; i++) 
        Console.Write((A + i * d) + " ");

    }

    // Driver code
    public static void Main()
    {
        int A = 20, B = 32, N = 5;
        printAMeans(A, B, N);
    }
}
// Contributed by vt_m
```

## PHP

```php
<?php
// PHP program to find n arithmetic 
// means between A and B

// Prints N arithmetic means 
// between A and B.
function printAMeans($A, $B, $N)
{

    // calculate common
    // difference(d)
    $d = ($B - $A) / ($N + 1);

    // for finding N the arithmetic 
    // mean between A and B
    for ($i = 1; $i <= $N; $i++) 
        echo ($A + $i * $d) ," "; 
}

    // Driver Code 
    $A = 20; $B = 32; 
    $N = 5;
    printAMeans($A, $B, $N);

// This code is Contributed by vt_m.
?>
```

**Output:**

```
22 24 26 28 30
```