# 理解 C

中的“register”关键字

> 原文:[https://www . geesforgeks . org/understanding-register-keyword/](https://www.geeksforgeeks.org/understanding-register-keyword/)

寄存器比内存存取快，所以 C 程序中最常用的变量可以用 *register* 关键字放入寄存器。关键字 *register* 提示编译器给定的变量可以放入寄存器。把它放入寄存器还是不放入寄存器是编译器的选择。一般来说，编译器自己进行优化，并将变量放入寄存器。

1)如果您对寄存器变量使用&运算符，编译器可能会给出错误或警告(取决于您使用的编译器)，因为当我们说变量是寄存器时，它可能存储在寄存器而不是内存中，并且寄存器的访问地址无效。试试下面的程序。

```cpp
#include<stdio.h>

int main()
{
    register int i = 10;
    int* a = &i;
    printf("%d", *a);
    getchar();
    return 0;
}
```

2) *register* 关键字可以和指针变量一起使用。显然，一个寄存器可以有一个存储单元的地址。下面的程序不会有任何问题。

```cpp
#include<stdio.h>

int main()
{
    int i = 10;
    register int* a = &i;
    printf("%d", *a);
    getchar();
    return 0;
}
```

3) Register 是一个存储类，C 不允许一个变量有多个存储类说明符。所以，*寄存器*不能和*静态*一起使用。试试下面的程序。

```cpp
#include<stdio.h>

int main()
{
    int i = 10;
    register static int* a = &i;
    printf("%d", *a);
    getchar();
    return 0;
}
```

4) Register 只能在一个块内(本地)使用，不能在*全局*范围内(主外)使用。

```cpp
#include <stdio.h>

// error (global scope)
register int x = 10;
int main()
{
    // works (inside a block)
    register int i = 10;
    printf("%d\n", i);
    printf("%d", x);
    return 0;
}
```

**编译错误:**

```cpp
prog.c:3:14: error: register name not specified for 'x'
 register int x = 10;//error (global scope)
              ^

```

5)C 程序中寄存器变量的数量没有限制，但重点是编译器可能会把一些变量放在寄存器中，而另一些则不会。

如果你在上面的文章中发现任何不正确的地方，或者你想分享更多关于 register 关键字的信息，请写评论。