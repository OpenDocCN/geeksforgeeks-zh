# 求数列 1 + 2 + 6 + 15 + 31 + 56 + 的第 n 项……

> 原文: [https://www.geeksforgeeks.org/find-the-nth-term-of-the-series-1-2-6-15-31-56/](https://www.geeksforgeeks.org/find-the-nth-term-of-the-series-1-2-6-15-31-56/)

给定一个整数`N`。任务是编写一个程序来找到给定系列的第`N`个术语:
```
1 + 2 + 6 + 15 + 31 + 56 + ... 
```

**示例**:
```
Input : N = 8
Output : 141

Input : N = 20
Output : 2471
```

## 进场
给定的系列是:
```
1, 2, 6, 15, 31, 56, 92, 141, ...
```

**第一个连续差**:
```
1 4 9 16 25 36 49 .......
```

**第二个连续差**:
```
3 5 7 9 11 13......
```

由于第二个连续的差异是在 AP 中，系列的第 n 项(`t_n`)是这样的形式，
`A(n–1)(n–2)(n–3)+B(n–1)(n–2)+C(n–1)+D`
所以，`t_n = A(n–1)(n–2)(n–3)+B(n–1)(n–2)+C(n–1)+D`
现在，
`t_1 = D = 1`
`t_2 = C(2–1)+D = 2`
`t_3 = 2B+2C+D = 6`
`t_4 = CA+6B+3C+D = 15`
通过求解上述四个方程，我们得到`A = 1/3`，`B = 3/2`，`C = 1`，`D = 1`。在将这些值代入`t_n`并简化后，我们得到
`t_{n} = \frac{2n^{3}-3n^{2}+n+6}{6}`

以下是上述方法的实现:

## C++
```cpp
// C++ program to find Nth
// term of the series:
// 1 + 2 + 6 + 15 + 31 + 56 + ...
#include<iostream>
#include<math.h>
using namespace std;

// calculate Nth term of given series
int Nth_Term(int n)
{
    return (2 * pow(n, 3) - 3 *
                pow(n, 2) + n + 6) / 6;
}

// Driver code
int main()
{
    int N = 8;
    cout << Nth_Term(N);
}
```

## Java
```java
// Java program to find Nth
// term of the series:
// 1 + 2 + 6 + 15 + 31 + 56 + ...
import java.util.*;
import java.lang.*;

class GFG
{
// calculate Nth term of given series
static double Nth_Term(int n)
{
    return (2 * Math.pow(n, 3) - 3 *
                Math.pow(n, 2) + n + 6) / 6;
}

// Driver code
static public void main (String args[])
{
    int N = 8;
    System.out.println(Nth_Term(N));
}
}

// This code is contributed
// by Akanksha Rai
```

## Python 3
```python
# Python program to find Nth term of the series:
# 1 + 2 + 6 + 15 + 31 + 56 + ...

# calculate Nth term of given series
def Nth_Term(n):
    return (2 * pow(n, 3) - 3 * pow(n, 2) + n + 6) // 6

# Driver code
N = 8
print(Nth_Term(N))
```

## C#
```csharp
// C# program to find Nth
// term of the series:
// 1 + 2 + 6 + 15 + 31 + 56 + ...
using System;

class GFG
{
// calculate Nth term of given series
static double Nth_Term(int n)
{
    return (2 * Math.Pow(n, 3) - 3 *
                Math.Pow(n, 2) + n + 6) / 6;
}

// Driver code
static public void Main ()
{
    int N = 8;
    Console.WriteLine(Nth_Term(N));
}
}

// This code is contributed
// by Sach_Code
```

## PHP
```php
<?php
// PHP program to find Nth
// term of the series:
// 1 + 2 + 6 + 15 + 31 + 56 + ..

// calculate Nth term of given series
function Nth_Term($n)
{
    return (2 * pow($n, 3) - 3 *
                pow($n, 2) + $n + 6) / 6;
}

// Driver code
$N = 8;

echo Nth_Term($N);

// This code is contributed by
// Shashank_Sharma
?>
```

## JavaScript
```javascript
<script>
// js program to find Nth
// term of the series:
// 1 + 2 + 6 + 15 + 31 + 56 + ..

// calculate Nth term of given series
function Nth_Term(n)
{
    return (2 * Math.pow(n, 3) - 3 *
                Math.pow(n, 2) + n + 6) / 6;
}

// Driver code
let N = 8;

document.write(Nth_Term(N));

// This code is contributed
// by pulamolu mohan pavan cse
</script>
```

**Output**:
```
141
```