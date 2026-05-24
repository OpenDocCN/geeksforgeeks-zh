# 求数列 3、14、39、84 的第 n 项……

> 原文: [https://www.geeksforgeeks.org/find-nth-term-of-the-series-3-14-39-84/](https://www.geeksforgeeks.org/find-nth-term-of-the-series-3-14-39-84/)

给定一个数字 `n`，任务是编写一个程序来寻找下面系列中的第 `n` 项:
> 3, 14, 39, 84…

**例:**

```
Input: 3
Output: 39
For N = 3
Nth term = ( 3*3*3 ) + ( 3*3 ) + 3
         = 39

Input: 4
Output: 84
```

计算级数第 `n` 项的公式:
```
Nth term = ( N*N*N ) + ( N*N ) + N 
```

下面是需要的实现:

## C++

```cpp
// CPP program to find N-th term of the series:
// 3, 14, 38, 84...
#include <iostream>
using namespace std;

// calculate Nth term of series
int nthTerm(int N)
{
    return (N * N * N) + (N * N) + N;
}

// Driver Function
int main()
{
    int N = 3;

    cout << nthTerm(N);

    return 0;
}
```

## Java

```java
// Java program to find Nth number
import java.io.*;

// calculate Nth term of this series
class GFG
{
    public int nthTerm(int N)
    {
        // By using above formula
        return (N * N * N) + (N * N) + N;
    }

    // Driver Code
    public static void main(String[] args)
    {
        int N = 3;
        GFG a = new GFG();

        // call and print Nth term
        System.out.println(a.nthTerm(N));
    }
}
```

## Python 3

```python
# Python 3 program to find  N-th
# term of the series:
# 3, 14, 38, 84...

# Function to calculate Nth term of series 
def nthTerm(n) :

    return (N * N * N) + (N * N) + N

# Driver code
if __name__ == "__main__" :

     N = 3

     # function calling
     print(nthTerm(N))

# This code is contributed by ANKITRAI1
```

## C#

```csharp
// C# program to find Nth number
using System;

// calculate Nth term of this series
class GFG
{
    public int nthTerm(int N)
    {
        // By using above formula
        return (N * N * N) + (N * N) + N;
    }

    // Driver Code
    public static void Main()
    {
        int N = 3;
        GFG a = new GFG();

        // call and print Nth term
        Console.WriteLine(a.nthTerm(N));
    }
}

// This code is contributed
// by inder_verma.
```

## PHP

```php
<?php
// PHP program to find N-th term 
// of the series: 3, 14, 38, 84...

// calculate Nth term of series
function nthTerm($N)
{
    return ($N * $N * $N) +
           ($N * $N) + $N;
}

// Driver Code
$N = 3;

echo nthTerm($N);

// This code is contributed
// by Shivi_Aggarwal
?>
```

## JavaScript

```javascript
<script>

// JavaScript program to find N-th term of the series:
// 3, 14, 38, 84...

// calculate Nth term of series
function nthTerm( N)
{
    return (N * N * N) + (N * N) + N;
}

// Driver Function

    let N = 3;
    document.write(nthTerm(N));

// This code contributed by Rajput-Ji

</script>
```

**Output:**

```