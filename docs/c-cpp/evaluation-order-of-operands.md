# 操作数的求值顺序

> 原文:[https://www.geeksforgeeks.org/evaluation-order-of-operands/](https://www.geeksforgeeks.org/evaluation-order-of-operands/)

考虑下面的程序。

## C++

```cpp
// C++ implementation
#include <bits/stdc++.h>
using namespace std;
int x = 0;

int f1()
{
    x = 5;
    return x;
}

int f2()
{
    x = 10;
    return x;
}

int main()
{
    int p = f1() + f2();
    cout << ("%d ", x);
    getchar();
    return 0;
}
```

## C

```cpp
#include <stdio.h>
int x = 0;

int f1()
{
    x = 5;
    return x;
}

int f2()
{
    x = 10;
    return x;
}

int main()
{
    int p = f1() + f2();
    printf("%d ", x);
    getchar();
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
class GFG {

    static int x = 0;

    static int f1()
    {
        x = 5;
        return x;
    }

    static int f2()
    {
        x = 10;
        return x;
    }

    public static void main(String[] args)
    {
        int p = f1() + f2();
        System.out.printf("%d ", x);
    }
}

// This code is contributed by Rajput-Ji
```

## 蟒蛇 3

```cpp
# Python3 implementation of the above approach
class A():
    x = 0;

    def f1():
        A.x = 5;
        return A.x;

    def f2():
        A.x = 10;
        return A.x;

# Driver Code
p = A.f1() + A.f2();
print(A.x);

# This code is contributed by mits
```

## C#

```cpp
// C# implementation of the above approach
using System;

class GFG {

    static int x = 0;

    static int f1()
    {
        x = 5;
        return x;
    }

    static int f2()
    {
        x = 10;
        return x;
    }

    // Driver code
    public static void Main(String[] args)
    {
        int p = f1() + f2();
        Console.WriteLine("{0} ", x);
    }
}

// This code has been contributed
// by 29AjayKumar
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP implementation of the above approach
$x = 0;

function f1()
{
    global $x;
    $x = 5;
    return $x;
}

function f2()
{
    global $x;
    $x = 10;
    return $x;
}

// Driver Code
$p = f1() + f2();
print($x);

// This code is contributed by mits
?>
```

## java 描述语言

```cpp
<script>
x = 0;

function f1()
{
    x = 5;
    return x;
}

function f2()
{
    x = 10;
    return x;
}

var p = f1() + f2();
document.write(x);

// This code is contributed by Amit Katiyar
</script>
```

**输出:**

```cpp
10
```

上述程序的输出是什么—“5”还是“10”？
输出未定义，因为标准未规定 f1() + f2()的评估顺序。编译器可以自由地首先调用 f1()或 f2()。只有当表达式中出现同等级别的优先运算符时，关联性才会出现。例如，f1() + f2() + f3()将被视为(f1() + f2()) + f3()。但是在第一对中，哪个函数(操作数)先被求值并不是由标准定义的。
感谢文基提出解决方案。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。