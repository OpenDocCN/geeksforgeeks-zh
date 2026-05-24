# C |集合 1 中的运算符(算术运算符)

> 原文:[https://www . geesforgeks . org/operators-in-c-set-1-算术-operators/](https://www.geeksforgeeks.org/operators-in-c-set-1-arithmetic-operators/)

![](img/7475cb9d2bc2dd61cbab802613738268.png)

运算符是任何编程语言的基础。因此，如果不使用运算符，C 语言的功能是不完整的。运算符允许我们对操作数执行不同类型的操作。在中，可将中的运算符分为以下几类:

*   **算术运算符** s (+，-，*，/，%，后递增，前递增，后递减，前递减)
*   **关系运算符** (==，！=，>，<，> = & < =)逻辑运算符(& &，|| and！)
*   **按位运算符** ( &、|、^、~、> >和< <)
*   **赋值运算符** s (=，+=，-=，*=，等等)
*   **其他运算符**(条件、逗号、大小写、地址、重定向)

**算术运算符:**这些用于对操作数执行算术/数学运算。属于这一类别的二元运算符有:

*   **加法:****“+”**运算符将两个操作数相加。例如 **x+y** 。
*   **减法:****“-”**运算符减去两个操作数。例如 **x-y** 。
*   **乘法:****' ***运算符将两个操作数相乘。例如 **x*y** 。
*   **除法:****/**运算符将第一个操作数除以第二个操作数。例如， **x/y** 。
*   **模数:**当第一个操作数除以第二个操作数时，**“%”**运算符返回余数。例如， **x%y** 。

## C

```cpp
// C program to demonstrate
// working of binary arithmetic
// operators
#include <stdio.h>

int main()
{
    int a = 10, b = 4, res;

    // printing a and b
    printf("a is %d and b is %d\n", a, b);

    res = a + b; // addition
    printf("a+b is %d\n", res);

    res = a - b; // subtraction
    printf("a-b is %d\n", res);

    res = a * b; // multiplication
    printf("a*b is %d\n", res);

    res = a / b; // division
    printf("a/b is %d\n", res);

    res = a % b; // modulus
    printf("a%%b is %d\n", res);

    return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 4, res;

    // printing a and b
    cout<<"a is "<<a<<" and b is "<<b<<"\n";

    // addition
    res = a + b; 
    cout << "a+b is: "<< res << "\n";

    // subtraction
    res = a - b; 
    cout << "a-b is: "<< res << "\n";

    // multiplication
    res = a * b; 
    cout << "a*b is: "<< res << "\n";

    // division
    res = a / b;
    cout << "a/b is: "<< res << "\n";

    // modulus
    res = a % b;
    cout << "a%b is: "<< res << "\n";

    return 0;
}
```

**输出:**

```cpp
a is 10 and b is: 4
a+b is: 14
a-b is: 6
a*b is: 40
a/b is: 2
a%b is: 2

```

属于一元算术运算符类别的有:

*   **增量:****“++”**运算符用于增加整数值。当放在变量名(也称为预递增运算符)之前时，其值会立即递增。例如 **++ x** 。
    当它被放在变量名(也称为后递增运算符)之后时，它的值会被暂时保留，直到执行该语句，并在执行下一条语句之前得到更新。例如 **x++** 。
*   **递减:****–‘**运算符用于递减整数值。当放在变量名(也称为预递减运算符)之前时，其值会立即递减。例如，**––x**。
    当它被放在变量名(也称为后减量运算符)之后时，它的值会被暂时保留，直到执行该语句，并在执行下一个语句之前得到更新。例如，**x–**。

## C

```cpp
// C program to demonstrate working
// of Unary arithmetic
// operators
#include <stdio.h>

int main()
{
    int a = 10, b = 4, res;

    // post-increment example:
    // res is assigned 10 only, a is not updated yet
    res = a++ ;
    printf("a is %d and res is %d\n", a,
           res); // a becomes 11 now

    // post-decrement example:
    // res is assigned 11 only, a is not updated yet
    res = a--;
    printf("a is %d and res is %d\n", a,
           res); // a becomes 10 now

    // pre-increment example:
    // res is assigned 11 now since
    // a is updated here itself
    res = ++ a;

    // a and res have same values = 11
    printf("a is %d and res is %d\n", a, res);

    // pre-decrement example:
    // res is assigned 10 only since a is updated here
    // itself
    res = --a;

    // a and res have same values = 10
    printf("a is %d and res is %d\n", a, res);

    return 0;
}
```

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a = 10, b = 4, res;

    // post-increment example:
    // res is assigned 10 only,
    // a is not updated yet
    res = a++ ;
    // a becomes 11 now
    cout << "a is " << a
         << " and res is "
         << res << "\n";

    // post-decrement example:
    // res is assigned 11 only,
    // a is not updated yet
    res = a--;
    // a becomes 10 now
    cout << "a is " << a
         << " and res is "
         << res << "\n";

    // pre-increment example:
    // res is assigned 11 now
    // since a is updated here itself
    res = ++ a;

    // a and res have same values = 11
    cout << "a is " << a
         << " and res is "
         << res << "\n";

    // pre-decrement example:
    // res is assigned 10 only
    // since a is updated here
    // itself
    res = --a;
    // a and res have same values = 10
    cout << "a is " << a
         << " and res is "
         << res << "\n";

    return 0;
}
```

**输出:**

```cpp
a is 11 and res is 10
a is 10 and res is 11
a is 11 and res is 11
a is 10 and res is 10

```

我们很快将讨论不同岗位的其他类别的操作员。
要了解**运算符优先级和关联性**，请参考[本](https://www.geeksforgeeks.org/c-operator-precedence-associativity/)链接:
[C](https://www.geeksforgeeks.org/c-language-2-gq/operators-gq/)
运算符小测验本文由 Ayush Jaggi 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论