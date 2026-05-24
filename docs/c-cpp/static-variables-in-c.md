# C 中的静态变量

> 原文:[https://www.geeksforgeeks.org/static-variables-in-c/](https://www.geeksforgeeks.org/static-variables-in-c/)

静态变量有一个属性，即使超出了它们的范围，也能保持它们的值！因此，静态变量在它们以前的作用域中保留它们以前的值，并且不会在新的作用域中再次初始化。
语法:

```cpp
static data_type var_name = var_value; 
```

以下是一些关于 c .
**(1)**中静态变量的有趣事实，当程序运行时，静态 int 变量会保留在内存中。当声明变量的函数调用结束时，普通或自动变量将被销毁。
例如，我们可以使用 static int 来统计函数被调用的次数，但是自动变量不能用于此目的。
例如，以下程序打印“1 2”

## C

```cpp
#include<stdio.h>
int fun()
{
  static int count = 0;
  count++ ;
  return count;
}

int main()
{
  printf("%d ", fun());
  printf("%d ", fun());
  return 0;
}
```

输出:

```cpp
1 2
```

但是下面程序打印 1 1

## C

```cpp
#include<stdio.h>
int fun()
{
  int count = 0;
  count++ ;
  return count;
}

int main()
{
  printf("%d ", fun());
  printf("%d ", fun());
  return 0;
}
```

输出:

```cpp
1 1
```

**2)** 静态变量是在数据段分配内存，而不是栈段。详见[C 程序的内存布局](https://www.geeksforgeeks.org/memory-layout-of-c-program/)。
**3)** 静态变量(如全局变量)如果没有显式初始化，则初始化为 0。例如，在下面的程序中，x 的值被打印为 0，而 y 的值是垃圾。详见[本](https://www.geeksforgeeks.org/g-fact-53/)。

## C

```cpp
#include <stdio.h>
int main()
{
    static int x;
    int y;
    printf("%d \n %d", x, y);
}
```

输出:

```cpp
0 
[some_garbage_value] 
```

**4)** 在 C 语言中，静态变量只能使用常量文字进行初始化。例如，以下程序编译失败。详见[本](https://www.geeksforgeeks.org/g-fact-80/)。

## C

```cpp
#include<stdio.h>
int initializer(void)
{
    return 50;
}

int main()
{
    static int i = initializer();
    printf(" value of i = %d", i);
    getchar();
    return 0;
}
```

输出

```cpp
 In function 'main':
9:5: error: initializer element is not constant
     static int i = initializer();
     ^
```

请注意，这个条件在 C++ 中不成立。所以如果你把程序保存为 C++ 程序，它会编译并运行良好。

**5)** 静态全局变量和函数在 C/C++ 中也是可以的。其目的是将变量或函数的范围限制在一个文件中。详情请参考 C 中的[静态功能。
**6)** 静态变量不应该在结构内部声明。原因是 C 编译器要求整个结构元素放在一起(即结构成员的内存分配应该是连续的)。可以在函数内部声明结构(堆栈段)或动态分配内存(堆段)，甚至可以是全局的(BSS 或数据段)。不管是什么情况，所有的结构成员都应该驻留在同一个内存段中，因为结构元素的值是通过计算元素相对于结构起始地址的偏移量来获取的。将一个成员单独分离到数据段违背了静态变量的目的，并且有可能使整个结构成为静态的。
**相关文章:**](https://www.geeksforgeeks.org/what-are-static-functions-in-c/) 

*   [c++ 中的静态关键字](https://www.geeksforgeeks.org/static-keyword-cpp/)
*   [静态关键词测验](https://www.geeksforgeeks.org/c-plus-plus-gq/static-keyword-gq/)
*   [c++ 中的静态数据成员](https://www.geeksforgeeks.org/stati/)
*   [静止物体什么时候被破坏？](https://www.geeksforgeeks.org/static-objects-destroyed/)
*   [关于静态成员函数的有趣事实](https://www.geeksforgeeks.org/some-interesting-facts-about-static-member-functions-in-c/)
*   [静态函数可以是虚函数吗？](https://www.geeksforgeeks.org/g-fact-29/)
*   [c++ 和 Java 中静态关键字的比较](https://www.geeksforgeeks.org/static-keyword-in-java/)
*   [C](https://www.geeksforgeeks.org/what-are-static-functions-in-c/)中的静态功能

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。