# 在 C 语言中，函数在声明前被调用会发生什么？

> 原文:[https://www.geeksforgeeks.org/g-fact-95/](https://www.geeksforgeeks.org/g-fact-95/)

在 C 语言中，如果一个函数在其声明之前被调用，**编译器假定该函数的返回类型为 int** 。
例如，以下程序编译失败。

## C

```cpp
#include <stdio.h>
int main(void)
{
    // Note that fun() is not declared
    printf("%c\n", fun());
    return 0;
}

char fun()
{
   return 'G';
}
```

如果上述代码中的函数 **char fun()** 是在 main()之前定义的，那么它不会编译成功。因为编译器默认假设返回类型为“int”。在声明时，如果返回类型与 int 不匹配，那么编译器会给出一个错误。

由于函数是在 main()之前定义的，因此以下程序编译并运行良好。

## C

```cpp
#include <stdio.h>

int fun()
{
   return 10;
}

int main(void)
{
    // Note the function fun() is declared
    printf("%d\n", fun());
    return 0;
}
```

**参数呢？**编译器对参数不做任何假设。因此，当函数应用于某些参数时，编译器将无法执行参数类型和 arity 的编译时检查。这可能会导致问题。例如，下面的程序在 GCC 中编译 fine 并产生垃圾值作为输出。

## C

```cpp
#include <stdio.h>

int main (void)
{
    printf("%d", sum(10, 5));
    return 0;
}
int sum (int b, int c, int a)
{
    return (a+b+c);
}
```

有一种误解，认为编译器假定输入参数也是 int。如果编译器假定输入参数为 int，上述程序将无法编译。
总是建议在使用之前先声明一个函数，这样我们在程序运行的时候就看不到任何惊喜了(详见[本](https://www.geeksforgeeks.org/importance-of-function-prototype-in-c/))。
**来源:**
[http://en.wikipedia.org/wiki/Function_prototype#Uses](http://en.wikipedia.org/wiki/Function_prototype#Uses)
如发现有不正确的地方，或想分享以上讨论话题的更多信息，请写评论