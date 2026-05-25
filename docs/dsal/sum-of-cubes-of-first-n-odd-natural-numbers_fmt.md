# 前 n 个奇数自然数的立方之和

> 原文：[https://www.geeksforgeeks.org/sum-of-cubes-of-first-n-odd-natural-numbers/](https://www.geeksforgeeks.org/sum-of-cubes-of-first-n-odd-natural-numbers/)

给定一个数 `n`，求前 `n` 个奇数自然数的和。

```
Input  : 2
Output : 28
1^3 + 3^3 = 28

Input  : 4
Output : 496
1^3 + 3^3 + 5^3 + 7^3 = 496
```

## 简单解法

一个`简单的解法`就是遍历 `n` 个奇数，求立方体的和。

### C++

```cpp
// Simple C++ method to find sum of cubes of
// first n odd numbers.
#include <iostream>
using namespace std;

int cubeSum(int n)
{
    int sum = 0;
    for (int i = 0; i < n; i++)
        sum += (2*i + 1)*(2*i + 1)*(2*i + 1);
    return sum;
}

int main()
{
    cout << cubeSum(2);
    return 0;
}
```

### Java

```java
// Java program to perform sum of
// cubes of first n odd natural numbers

public class GFG
{

    public static int cubesum(int n)
    {
        int sum = 0;
        for(int i = 0; i < n; i++)
            sum += (2 * i + 1) * (2 * i +1)
                   * (2 * i + 1);

        return sum;
    }

    // Driver function
    public static void main(String args[])
    {
        int a = 5;
        System.out.println(cubesum(a));

    }
}

// This article is published Akansh Gupta
```

### Python 3

```python
# Python3 program to find sum of
# cubes of first n odd numbers.

def cubeSum(n):
    sum = 0

    for i in range(0, n) :
        sum += (2 * i + 1) * (2 * i + 1) * (2 * i + 1)
    return sum

# Driven code
print(cubeSum(2))

# This code is contributed by Shariq Raza
```

### C#

```csharp
// C# program to perform sum of
// cubes of first n odd natural numbers
using System;

public class GFG
{

    public static int cubesum(int n)
    {
        int sum = 0;
        for(int i = 0; i < n; i++)
            sum += (2 * i + 1) * (2 * i +1)
                   * (2 * i + 1);

        return sum;
    }

    // Driver function
    public static void Main()
    {
        int a = 5;
        Console.WriteLine(cubesum(a));

    }
}

// This code is published vt_m
```

### PHP

```php
<?php
// Simple PHP method to find sum of
// cubes of first n odd numbers.

function cubeSum($n)
{
    $sum = 0;
    for ($i = 0; $i < $n; $i++)
        $sum += (2 * $i + 1) *
                (2 * $i + 1) *
                (2 * $i + 1);
    return $sum;
}

// Driver Code
echo cubeSum(2);

// This code is contributed by vt_m.
?>
```

### JavaScript

```javascript
<script>
// Simple javascript method to find sum of cubes of
// first n odd numbers.
function cubeSum( n)
{
    let sum = 0;
    for (let i = 0; i < n; i++)
        sum += (2*i + 1)*(2*i + 1)*(2*i + 1);
    return sum;
}

    document.write(cubeSum(2));

// This code is contributed by Rajput-Ji

</script>
```

## 高效解法

一个`有效的解决方案`是应用下面的公式。

```
sum = n^2(2n^2 - 1)
```

**它是如何工作的？**

我们知道前 `n` 个自然数的立方和是 `n^2(n+1)^2 / 4`。

前 `n` 个偶数的和是 `2 * n^2(n+1)^2`。

前 `n` 个奇数自然数的立方和 = 前 `2n` 个自然数的立方和 - 前 `n` 个偶数的立方和。

```
= (2n)^2(2n+1)^2 / 4 - 2 * n^2(n+1)^2
= n^2(2n+1)^2 - 2 * n^2(n+1)^2
= n^2[(2n+1)^2 - 2*(n+1)^2]
= n^2(2n^2 - 1)
```

### C++

```cpp
// Efficient C++ method to find sum of cubes of
// first n odd numbers.
#include <iostream>
using namespace std;

int cubeSum(int n)
{
    return n * n * (2 * n * n - 1);
}

int main()
{
    cout << cubeSum(4);
    return 0;
}
```

### Java

```java
// Java program to perform sum of
// cubes of first n odd natural numbers

public class GFG
{
    public static int cubesum(int n)
    {

        return (n) * (n) * (2 * n * n - 1);
    }

    // Driver function
    public static void main(String args[])
    {
        int a = 4;
        System.out.println(cubesum(a));

    }
}

// This code is contributed by Akansh Gupta.
```

### Python 3

```python
# Python3 program to find sum of
# cubes of first n odd numbers.

# Function to find sum of cubes
# of first n odd number
def cubeSum(n):
    return (n * n * (2 * n * n - 1))

# Driven code
print(cubeSum(4))

# This code is contributed by Shariq Raza
```

### C#

```csharp
// C# program to perform sum of
// cubes of first n odd natural numbers
using System;

public class GFG
{
    public static int cubesum(int n)
    {

        return (n) * (n) * (2 * n * n - 1);
    }

    // Driver function
    public static void Main()
    {
        int a = 4;
        Console.WriteLine(cubesum(a));

    }
}

// This code is published vt_m.
```

### PHP

```php
<?php
// Efficient PHP method to
// find sum of cubes of
// first n odd numbers.

function cubeSum($n)
{
    return $n * $n * (2 * $n * $n - 1);
}

// Driver Code
echo cubeSum(4);

// This code is contributed by vt_m.
?>
```

### JavaScript

```javascript
<script>
// javascript program to perform sum of
// cubes of first n odd natural numbers

function cubesum(n)
{

    return (n) * (n) * (2 * n * n - 1);
}

// Driver function
var a = 4;
document.write(cubesum(a));

// This code is contributed by Amit Katiyar
</script>
```

本文由**达曼德拉·库马尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。