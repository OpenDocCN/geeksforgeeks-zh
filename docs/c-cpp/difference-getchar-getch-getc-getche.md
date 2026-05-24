# 【getc()、getchar()、getch()和 getche() 之间的差异

> 原文:[https://www . geesforgeks . org/difference-getchar-getch-getc-getche/](https://www.geeksforgeeks.org/difference-getchar-getch-getc-getche/)

所有这些函数从输入中读取一个字符并返回一个整数值。返回该整数以容纳用于指示失败的特殊值。EOF 值通常用于此目的。

<u>**getc():**</u>
它从给定的输入流中读取单个字符，并在成功时返回相应的整数值(通常是读取字符的 ASCII 值)。失败时返回电渗流。

语法:

```cpp
int getc(FILE *stream); 
```

示例:

```cpp
// Example for getc() in C
#include <stdio.h>
int main()
{
   printf("%c", getc(stdin));
   return(0);
}
```

```cpp
Input: g (press enter key)
Output: g 
```

示例应用程序:[比较两个文件并报告不匹配的 C 程序](https://www.geeksforgeeks.org/c-program-compare-two-files-report-mismatches/)

<u>**getchar():**</u>
getc()和 getchar()的区别在于 getc()可以从任何输入流读取，但是 getchar()从标准输入读取。所以 getchar()相当于 getc(stdin)。

语法:

```cpp
int getchar(void); 
```

示例:

```cpp
// Example for getchar() in C
#include <stdio.h>
int main()
{
   printf("%c", getchar());
   return 0;
}
```

```cpp
Input: g(press enter key)
Output: g 
```

<u>**getch():**</u>
getch()是一个非标准函数，存在于像 Turbo C 这样的 MS-DOS 编译器大多使用的 conio.h 头文件中，它不是 C 标准库或 ISO C 的一部分，也不是 POSIX 定义的(来源:http://en.wikipedia.org/wiki/Conio.h)
和上述函数一样，它也是从键盘读取单个字符。但是它不使用任何缓冲区，所以输入的字符会立即返回，而无需等待回车键。
语法:

```cpp
int getch();
```

示例:

```cpp
// Example for getch() in C
#include <stdio.h>
#include <conio.h>
int main()
{
   printf("%c", getch());   
   return 0;
}
```

```cpp
Input:  g (Without enter key)
Output: Program terminates immediately.
        But when you use DOS shell in Turbo C, 
        it shows a single g, i.e., 'g'
```

<u>**【getche()】**</u>
与 getch()一样，这也是 conio.h 中存在的一个非标准功能，它从键盘上读取单个字符，并立即显示在输出屏幕上，无需等待回车键。

语法:

```cpp
int getche(void); 
```

示例:

```cpp
#include <stdio.h>
#include <conio.h>
// Example for getche() in C
int main()
{
  printf("%c", getche());
  return 0;
}
```

```cpp
Input: g(without enter key as it is not buffered)
Output: Program terminates immediately.
        But when you use DOS shell in Turbo C, 
        double g, i.e., 'gg'
```

本文由 **Vankayala Karunakar** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。