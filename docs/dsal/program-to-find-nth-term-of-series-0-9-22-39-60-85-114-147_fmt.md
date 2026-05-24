# 求数列 0，9，22，39，60，85，114，147 的第 n 项的程序

> 原文：[https://www.geeksforgeeks.org/program-to-find-nth-term-of-series-0-9-22-39-60-85-114-147/](https://www.geeksforgeeks.org/program-to-find-nth-term-of-series-0-9-22-39-60-85-114-147/)

给定一个数字 `n`，任务是编写一个程序来找到下面系列的第 `n` 项：
> 0, 9, 22, 39, 60, 85, 114, 147…..

## 例

```
Input: N = 4
Output: 39
For N = 4
4th Term = ( 2 * 4 * 4 + 3 * 4 - 5) 
         = 39

Input: N = 10
Output: 224
```

## 方法

本系列的广义第 `n` 项：
下面是需要的实现：

### C++

```cpp
// C++ program to find the N-th term of the series:
// 0, 9, 22, 39, 60, 85, 114, 147.....
#include <iostream>
#include <math.h>
using namespace std;

// calculate Nth term of series
int nthTerm(int n)
{
    return 2 * pow(n, 2) + 3 * n - 5;
}

// Driver code
int main()
{
    int N = 4;

    cout << nthTerm(N) << endl;

    return 0;
}
```

### Java

```java
// Java program to find the N-th term of the series:
// 0, 9, 22, 39, 60, 85, 114, 147.....

public class GFG {

    // calculate Nth term of series
    static int nthTerm(int n)
    {
        return 2 * (int)Math.pow(n, 2) + 3 * n - 5;
    }

    // Driver code
    public static void main(String args[])
    {
        int N = 4;

       System.out.println(nthTerm(N));

    }
    // This Code is contributed by ANKITRAI1
}
```

### Python 3

```python
# Python3 program to find the
# N-th term of the series:
# 0, 9, 22, 39, 60, 85, 114, 147.....

# calculate Nth term of series
def nthTerm(n):

    return 2 * pow(n, 2) + 3 * n - 5

# Driver code
N = 4
print(nthTerm(N))

# This code is contributed by
# Sanjit_Prasad
```

### C#

```csharp
// C# program to find the
// N-th term of the series:
// 0, 9, 22, 39, 60, 85, 114, 147.....
using System;

class GFG
{

// calculate Nth term of series
static int nthTerm(int n)
{
    return 2 * (int)Math.Pow(n, 2) +
                        3 * n - 5;
}

// Driver code
public static void Main()
{
    int N = 4;

    Console.WriteLine(nthTerm(N));
}
}

// This Code is contributed
// by Akanksha Rai(Abby_akku)
```

### PHP

```php
<?php
// PHP program to find the
// N-th term of the series:
// 0, 9, 22, 39, 60, 85, 114, 147.....

// calculate Nth term of series
function nthTerm($n)
{
    return 2 * pow($n, 2) +
           3 * $n - 5;
}

// Driver code
$N = 4;
echo nthTerm($N)."\n";

// This code is contributed
// by ChitraNayal
?>
```

### JavaScript

```javascript
<script>
// JavaScript program to find the N-th term of the series:
// 0, 9, 22, 39, 60, 85, 114, 147.....

// calculate Nth term of series
function nthTerm( n)
{
    return 2 * Math.pow(n, 2) + 3 * n - 5;
}

// Driver code

    let N = 4;

    document.write(nthTerm(N));

// This code contributed by gauravrajput1

</script>
```

## 输出

```
39
```

## 时间复杂度

O(1)