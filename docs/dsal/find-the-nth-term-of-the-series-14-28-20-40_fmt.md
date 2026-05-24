# 求数列 14，28，20，40 的第 n 项，…..

> 原文: [https://www.geeksforgeeks.org/find-the-nth-term-of-the-series-14-28-20-40/](https://www.geeksforgeeks.org/find-the-nth-term-of-the-series-14-28-20-40/)

给定一个数字 `N`。任务是在以下系列中找到第 `N` 个术语:

> **14，28，20，40，32，64…..**

**例:**

```
Input : N = 5
Output : 32

Input : N = 6
Output : 64
```

**进场:**

1.  用 14 初始化第一个数字。
2.  运行从 `i = 2` 到 `N` 的循环，并执行以下步骤:
    *   对于偶数 `i`，是上一项的两倍。例如，如果 `i = 2`，当前项将是 `2 * (i = 1 时的项)`，即 `2 * 14 = 28`。
    *   对于奇数 `i`，从上一项减去 8。
    *   退出循环并打印最终数字。

以下是上述方法的实现:

## C++

```cpp
// CPP program to find the Nth term of
// the series 14, 28, 20, 40, …..

#include <iostream>
using namespace std;

// Function to find the N-th term
int findNth(int N)
{
    // initializing the 1st number
    int b = 14;

    int i;

    // loop from 2nd term to nth term
    for (i = 2; i <= N; i++) {
        // if i is even, double the
        // previous number
        if (i % 2 == 0)
            b = b * 2;
        // if i is odd, subtract 8 from
        // previous number
        else
            b = b - 8;
    }

    return b;
}

// Driver Code
int main()
{
    int N = 6;

    cout << findNth(N);

    return 0;
}
```

## Java

```java
// Java program to find the Nth term of
// the series 14, 28, 20, 40,

import java.io.*;

class GFG {

// Function to find the N-th term
 static int findNth(int N)
{
    // initializing the 1st number
    int b = 14;

    int i;

    // loop from 2nd term to nth term
    for (i = 2; i <= N; i++) {
        // if i is even, double the
        // previous number
        if (i % 2 == 0)
            b = b * 2;
        // if i is odd, subtract 8 from
        // previous number
        else
            b = b - 8;
    }

    return b;
}

// Driver Code

    public static void main (String[] args) {
        int N = 6;

    System.out.print(findNth(N));
    }
}
// This code is contributed by shs
```

## Python 3

```python
# Python 3 program to find the Nth term
# of the series 14, 28, 20, 40, …..

# Function to find the N-th term
def findNth(N):

    # initializing the 1st number
    b = 14

    # loop from 2nd term to nth term
    for i in range (2, N + 1):

        # if i is even, double the
        # previous number
        if (i % 2 == 0):
            b = b * 2

        # if i is odd, subtract 8 from
        # previous number
        else:
            b = b - 8

    return b

# Driver Code
N = 6

print(findNth(N))

# This code is contributed
# by Akanksha Rai
```

## C#

```csharp
// C# program to find the Nth term of
// the series 14, 28, 20, 40,

using System;

public class GFG{
    // Function to find the N-th term
static int findNth(int N)
{
    // initializing the 1st number
    int b = 14;

    int i;

    // loop from 2nd term to nth term
    for (i = 2; i <= N; i++) {
        // if i is even, double the
        // previous number
        if (i % 2 == 0)
            b = b * 2;
        // if i is odd, subtract 8 from
        // previous number
        else
            b = b - 8;
    }

    return b;
}

// Driver Code

    static public void Main (){
    int N = 6;
    Console.WriteLine(findNth(N));
    }
}
// This code is contributed by ajit
```

## PHP

```php
<?php
// PHP program to find the Nth term of
// the series 14, 28, 20, 40, …..

// Function to find the N-th term
function findNth($N)
{
    // initializing the 1st number
    $b = 14;

    // loop from 2nd term to nth term
    for ($i = 2; $i <= $N; $i++)
    {
        // if i is even, double the
        // previous number
        if ($i % 2 == 0)
            $b = $b * 2;

        // if i is odd, subtract 8 from
        // previous number
        else
            $b = $b - 8;
    }
    return $b;
}

// Driver Code
$N = 6;
echo findNth($N);

// This code is contributed by akt_mit
?>
```

## JavaScript

```javascript
<script>

// java script program to find the Nth term of
// the series 14, 28, 20, 40, …..

// Function to find the N-th term
function findNth(N)
{
    // initializing the 1st number
    let b = 14;

    // loop from 2nd term to nth term
    for (let i = 2; i <= N; i++)
    {
        // if i is even, double the
        // previous number
        if (i % 2 == 0)
            b = b * 2;

        // if i is odd, subtract 8 from
        // previous number
        else
            b = b - 8;
    }
    return b;
}

// Driver Code
N = 6;
document.write(findNth(N));

// This code is contributed
// by pulamolu mohan pavan cse
</script>
```

**Output:**

```
64
```