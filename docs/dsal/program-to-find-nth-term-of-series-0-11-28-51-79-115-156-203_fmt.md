# 求数列第 n 项的程序

> 原文: [https://www.geeksforgeeks.org/program-to-find-nth-term-of-series-0-11-28-51-79-115-156-203/](https://www.geeksforgeeks.org/program-to-find-nth-term-of-series-0-11-28-51-79-115-156-203/)

给定一个数字 `n`，任务是编写一个程序来找到下面数列的第 `n` 项：
> 0, 11, 28, 51, 79, 115, 156, 203…..

## 示例

```
Input: N = 4
Output: 51
For N = 4
4th Term = ( 3 * 4 * 4 + 2 * 4 - 5) 
         = 51

Input: N = 10
Output: 314
```

## 方法

本数列的广义第 `n` 项公式为：`3 * n^2 + 2 * n - 5`。

下面是需要的实现：

## C++

```cpp
// CPP program to find the N-th term of the series:
// 0, 11, 28, 51, 79, 115, 156, 203.....
#include <iostream>
#include <math.h>
using namespace std;

// calculate Nth term of series
int nthTerm(int n)
{
    return 3 * pow(n, 2) + 2 * n - 5;
}

// Driver code
int main()
{
    int N = 4;

    cout << nthTerm(N) << endl;

    return 0;
}
```

## Java

```java
// Java program to find the
// N-th term of the series:
// 0, 11, 28, 51, 79, 115, 156, 203.....
import java.io.*;

class GFG
{

// calculate Nth term of series
static int nthTerm(int n)
{
    return 3 * (int) Math.pow(n, 2) +
                                 2 * n - 5;
}

// Driver code
public static void main (String[] args)
{
    int N = 4;

    System.out.println(nthTerm(N));
}
}

// This code is contributed
// by anuj_67
```

## Python 3

```python
# Python3 program to find the
# N-th term of the series:
# 0, 11, 28, 51, 79, 115, 156, 203.....

# calculate Nth term of series
def nthTerm(n):

    return 3 * pow(n, 2) + 2 * n - 5

# Driver code
N = 4
print(nthTerm(N))

# This code is contributed by
# Sanjit_Prasad
```

## C#

```csharp
// C# program to find the
// N-th term of the series:
// 0, 11, 28, 51, 79, 115, 156, 203.....
using System;

class GFG
{

// calculate Nth term of series
static int nthTerm(int n)
{
    return 3 * (int) Math.Pow(n, 2) +
                               2 * n - 5;
}

// Driver code
public static void Main ()
{
    int N = 4;

    Console.WriteLine(nthTerm(N));
}
}

// This code is contributed
// by inder_verma
```

## PHP

```php
<?php
// PHP program to find the
// N-th term of the series:
// 0, 11, 28, 51, 79, 115, 156, 203.....

// calculate Nth term of series
function nthTerm($n)
{
    return 3 * pow($n, 2) + 2 * $n - 5;
}

// Driver code
$N = 4;

echo nthTerm($N) . "\n";

// This code is contributed
// by Akanksha Rai(Abby_akku)
```

## JavaScript

```javascript
<script>
// JavaScript program to find the N-th term of the series:
// 0, 11, 28, 51, 79, 115, 156, 203.....

// calculate Nth term of series
function nthTerm( n)
{
    return 3 * Math.pow(n, 2) + 2 * n - 5;
}

// Driver code
let N = 4;

    document.write( nthTerm(N));

// This code contributed by gauravrajput1

</script>
```

**输出:**

```
51
```

### 复杂度

**时间复杂度:** `O(1)`