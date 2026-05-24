# 链接器如何解析在多个位置定义的全局符号？

> 原文:[https://www . geesforgeks . org/how-linkers-resolve-multiple-defined-global-symbols/](https://www.geeksforgeeks.org/how-linkers-resolve-multiply-defined-global-symbols/)

在编译时，编译器将每个全局符号作为强符号或弱符号导出到汇编程序，汇编程序将这些信息隐式编码在可重定位目标文件的符号表中。函数和初始化的全局变量得到强符号。未初始化的全局变量获得弱符号。
对于下面的示例程序，buf、bufp0、main 和 swap 是强符号；bufp1 是一个弱符号。

```cpp
/* main.c */
 void swap();
 int buf[2] = {1, 2};
 int main()
 {
   swap();
   return 0;
 }

 /* swap.c */
 extern int buf[];

 int *bufp0 = &buf[0];
 int *bufp1;

 void swap()
 {
   int temp;

   bufp1 = &buf[1];
   temp = *bufp0;
   *bufp0 = *bufp1;
   *bufp1 = temp;
}
```

给定强符号和弱符号的概念，Unix 链接器使用以下规则来处理多个已定义的符号:
**规则 1:** 不允许多个强符号(具有相同的变量名)。
**规则二:**给定一个强符号和多个弱符号，选择强符号。
**规则 3:** 给定多个弱符号，选择任意一个弱符号。
例如，假设我们试图编译并链接以下两个 C 模块:

```cpp
/* foo1.c */       
int main()          
{                   
  return 0;       
}                  

/* bar1.c */
int main()
{
  return 0;
}
```

在这种情况下，链接器将生成错误消息，因为强符号 main 被定义了多次(**规则 1** ):

```cpp
$ gcc foo1.c bar1.c
/tmp/cca015022.o: In function ‘main’:
/tmp/cca015022.o(.text+0x0): multiple definition of ‘main’
/tmp/cca015021.o(.text+0x0): first defined here

```

同样，链接器将为以下模块生成错误消息，因为强符号 x 被定义了两次(**规则 1** ):

```cpp
/* foo2.c */
int x = 15213;
int main()
{
  return 0;
}

/* bar2.c */
int x = 15213;
void f()
{
}
```

但是，如果 x 在一个模块中未初始化，则链接器将悄悄地选择在另一个模块中定义的强符号(**规则 2** )，如以下程序中的情况:

```cpp
/* foo3.c */
#include <stdio.h>
void f(void);
int x = 15213;
int main()
{
  f();
  printf("x = %d\n", x);
  return 0;
}

/* bar3.c */
int x;
void f()
{
  x = 15212;
}
```

在运行时，函数 f()将 x 的值从 15213 更改为 15212，这对于函数 main 的作者来说可能是一个不受欢迎的惊喜！请注意，链接器通常不会显示它检测到 x 的多个定义。

```cpp
$ gcc -o gfg foo3.c bar3.c
$ ./gfg
x = 15212

```

如果 x 有两个弱定义(**规则 3** )也会发生同样的事情:

```cpp
/*a.c*/
#include <stdio.h>
void b(void);

int x;
int main()
{
    x = 2016;
    b();
    printf("x = %d ",x);
    return 0;
}
/*b.c*/
#include <stdio.h>

int x;

void b()
{
    x = 2017;

}
```

规则 2 和 3 的**应用会引入一些阴险的运行时错误，对于粗心的程序员来说是不可理解的，尤其是如果重复的符号定义有不同的类型。
例:“x”在一个模块中定义为 int，在另一个模块中定义为 double。**

```cpp
/*a.c*/
#include <stdio.h>
void b(void); 

int x = 2016;
int y = 2017;
int main()
{
    b();
    printf("x = 0x%x y = 0x%x \n", x, y);
    return 0;
}
/*b.c*/
double x;

void b()
{
    x = -0.0;
}
```

**执行:**

```cpp
$ gcc a.c b.c -o geeksforgeeks
$ ./geeksforgeeks
x = 0x0 y = 0x80000000

```

这是一个微妙而令人讨厌的错误，尤其是因为它是在没有编译系统警告的情况下无声无息地发生的，并且因为它通常在程序执行的很晚的时候才显现出来，远离错误发生的地方。在一个有数百个模块的大系统中，这种错误极难修复，尤其是因为许多程序员不知道链接器是如何工作的。有疑问时，使用 gcc -fno-common 标志等标志调用链接器，如果遇到多个已定义的全局符号，则会触发错误。

来源:http://csapp.cs.cmu.edu/public/ch7-preview.pdf

本文由 **[萨赫勒拉吉普特](https://www.linkedin.com/in/sahil-rajput-3ba2b3134/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。