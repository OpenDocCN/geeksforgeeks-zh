# 程序寻找数列 7, 21, 49, 91, 147, 217 的第 n 项

> 原文: [https://www.geeksforgeeks.org/program-to-find-nth-term-of-series-7-21-49-91-147-217/](https://www.geeksforgeeks.org/program-to-find-nth-term-of-series-7-21-49-91-147-217/)

给定一个数字 `n`，任务是编写一个程序来找到下面数列的第 `n` 项：
> 7, 21, 49, 91, 147, 217, 301, 399…… (共 N 项)

**示例**:
```
Input: N = 4
Output: 91
For N = 4
4th Term = ( 7 * 4 * 4 - 7 * 4 + 7) 
         = 91

Input: N = 10
Output: 636
```

给定的数列是：
> 7, 21, 49, 91, 147, 217, 301, 399, …..

从所有项中抽取公因子 7，我们得到：
> 7 * (1, 3, 7, 13, 21, 31, …..), …..

现在，对于内部数列：1, 3, 7, 13, 21, …
仔细观察，我们可以将上述数列的项表示为：
1 = (1<sup>2</sup>) – (1-1)
3 = (2<sup>2</sup>) – (2-1)
7 = (3<sup>2</sup>) – (3-1)
13 = (4<sup>2</sup>) – (4-1)
……
第 `n` 项 = (n<sup>2</sup>) – (n-1)

因此，实际数列的第 `n` 项将为：
```
N-th term = 7 * ((n^2) - (n-1))
          = 7 * (n^2 - n + 1)
```

下面是上述方法的实现：

## C++

```cpp
// C++ program to find the N-th term of the series:
// 7, 21, 49, 91, 146, 217, 301, 399, ...
#include <iostream>
#include <math.h>
using namespace std;

// calculate Nth term of series
int nthTerm(int n)
{
    return 7 * pow(n, 2) - 7 * n + 7;
}

// Driver code
int main()
{
    int N = 4;

    cout << nthTerm(N);

    return 0;
}
```

## Java

```java
// Java program to find the N-th term of the series:
// 7, 21, 49, 91, 146, 217, 301, 399, ...

// calculate Nth term of series
import java.util.*;

class solution
{

//Function to find the nth term of the series
static int nthTerm(int n)
{
    return 7 * (int)Math.pow(n, 2) - 7 * n + 7;
}

// Driver code
public static void main(String arr[])
{
    int N = 4;

    System.out.println(nthTerm(N));

}

}
```

## Python 3

```python
# Python3 program to find the N-th term of the series:
# 7, 21, 49, 91, 146, 217, 301, 399, ...

# calculate Nth term of series
def nthTerm( n):

    return 7 * pow(n, 2) - 7 * n + 7

# Driver code
N = 4

print(nthTerm(N))
```

## C#

```csharp
// C# program to find the
// N-th term of the series:
// 7, 21, 49, 91, 146, 217, 301, 399, ...
using System;

// calculate Nth term of series
class GFG
{

// Function to find the Nth
// term of the series
static int nthTerm(int n)
{
    return 7 * (int)Math.Pow(n, 2) - 7 * n + 7;
}

// Driver code
public static void Main()
{
    int N = 4;

    Console.WriteLine(nthTerm(N));
}
}

// This code is contributed
// by Akanksha Rai
```

## PHP

```php
<?php
// PHP program to find the
// N-th term of the series:
// 7, 21, 49, 91, 146, 217, 301, 399, ...
function Sum_upto_nth_Term($n)
{
    $r = 7 * pow($n, 2) - 7 * $n + 7;
    echo $r;
}

// Driver code
$N = 4;
Sum_upto_nth_Term($N);

// This code is contributed
// by Sanjit_Prasad
?>
```

## JavaScript

```javascript
<script>

// Javascript program to find the N-th term
// of the series:
// 7, 21, 49, 91, 146, 217, 301, 399, ...

// Calculate Nth term of series
function nthTerm(n)
{
    return 7 * Math.pow(n, 2) - 7 * n + 7;
}

// Driver code
let N = 4;

document.write(nthTerm(N));

// This code is contributed by Surbhi Tyagi.

</script>
```

**Output:**
```
91
```

**时间复杂度:** `O(1)`