# 不使用++或--

增加一个数字

> 原文: [https://www.geeksforgeeks.org/increment-a-number-without-using-or/](https://www.geeksforgeeks.org/increment-a-number-without-using-or/)

任务是在不使用`++`和`--`运算符的情况下递增一个数字。

**例:**

```
Input : 3
Output : 4

Input : 9
Output : 10
```

这个想法是基于这样一个事实:负数是用[2 的补码形式](https://www.geeksforgeeks.org/1s-2s-complement-binary-number/)存储的。2 的补码形式是通过反转位然后加 1 得到的。所以，如果我们把给定数字的所有位反转，并应用负号，我们得到的是数字加 1。

## C++

```cpp
// CPP program to increment an unsigned
// int using bitwise operators.
#include <bits/stdc++.h>
using namespace std;

// function that increment the value.
int increment(unsigned int i)
{
    // Invert bits and apply negative sign
    i = -(~i);

    return i;
}

// Driver code
int main()
{
    int n = 3;
    cout << increment(n);
    return 0;
}
```

## Java

```java
// Java program to increment
// an unsigned int using
// bitwise operators.
import java.io.*;

class GFG
{

// function that increment
// the value.
static long increment(long i)
{
    // Invert bits and
    // apply negative sign
    i = -(~i);

    return i;
}

// Driver code
public static void main (String[] args)
{
    long n = 3;
    System.out.print( increment(n));
}
}

// This code is contributed
// by inder_verma.
```

## Python 3

```python
# Python3 program to increment
# an unsigned int using
# bitwise operators.

# function that increment the value.
def increment(i):
    # Invert bits and
    # apply negative sign
    i = -(~i);

    return i;

# Driver code
if __name__ == "__main__":
    n = 3;
    print(increment(n));

# This code is contributed by mits
```

## C#

```csharp
// C# program to increment
// an unsigned int using
// bitwise operators.
using System;

class GFG
{

// function that increment
// the value.
static long increment(long i)
{
    // Invert bits and
    // apply negative sign
    i = -(~i);

    return i;
}

// Driver code
public static void Main ()
{
    long n = 3;
    Console.WriteLine(increment(n));
}
}

// This code is contributed
// by inder_verma.
```

## PHP

```php
<?php
// PHP program to increment
// an unsigned int using
// bitwise operators.

// function that increment the value.
function increment($i)
{
    // Invert bits and
    // apply negative sign
    $i = -(~$i);

    return $i;
}

// Driver code
$n = 3;
echo increment($n);

// This code is contributed by mits
?>
```

## JavaScript

```javascript
<script>
// Javascript program to increment an unsigned
// int using bitwise operators.

// function that increment the value.
function increment(i) {
    // Invert bits and apply negative sign
    i = -(~i);

    return i;
}

// Driver code

let n = 3;
document.write(increment(n));

// This code is contributed by _saurabh_jaiswal

</script>
```

**Output:**

```
4
```