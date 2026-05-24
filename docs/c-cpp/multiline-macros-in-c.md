# C

中的多行宏

> 原文:[https://www.geeksforgeeks.org/multiline-macros-in-c/](https://www.geeksforgeeks.org/multiline-macros-in-c/)

在本文中，我们将讨论如何编写多行宏。我们可以像函数一样编写多行宏，但是每个语句都以“\”结尾。让我们举个例子来看看。下面是简单宏，接受用户输入数字，打印输入数字是偶数还是奇数。

```cpp
#include <stdio.h>

#define MACRO(num, str) {\
            printf("%d", num);\
            printf(" is");\
            printf(" %s number", str);\
            printf("\n");\
           }

int main(void)
{
    int num;

    printf("Enter a number: ");
    scanf("%d", &num);

    if (num & 1)
        MACRO(num, "Odd");
    else
        MACRO(num, "Even");

    return 0;
}
```

乍一看，代码看起来还可以，但是当我们试图编译这段代码时，它会给出编译错误。

```cpp
[narendra@/media/partition/GFG]$ make macro
cc     macro.c   -o macro
macro.c: In function ‘main’:
macro.c:19:2: error: ‘else’ without a previous ‘if’
make: *** [macro] Error 1
[narendra@/media/partition/GFG]$ 

```

让我们看看我们在编写宏时犯了什么错误。我们用花括号把宏括起来。根据 C 语言规则，每个 C 语句都应该以分号结束。这就是为什么我们用分号来结束 MACRO。这是一个错误。让我们看看编译是如何扩展这个宏的。

```cpp
if (num & 1)
{
    -------------------------
    ---- Macro expansion ----
    -------------------------
};    /* Semicolon at the end of MACRO, and here is ERROR */

else 
{
   -------------------------
   ---- Macro expansion ----
   -------------------------

};

```

我们已经用分号结束了宏。编译器在展开宏时，会在“if”语句后加上分号。因为“if 和 else 语句”之间的分号，编译器给出编译错误。如果我们忽略“其他”部分，上面的程序可以正常工作。

为了克服这个限制，我们可以将宏放在“do-while(0)”语句中。我们修改后的宏将如下所示。

```cpp
#include <stdio.h>

#define MACRO(num, str) do {\
            printf("%d", num);\
            printf(" is");\
            printf(" %s number", str);\
            printf("\n");\
           } while(0)

int main(void)
{
    int num;

    printf("Enter a number: ");
    scanf("%d", &num);

    if (num & 1)
        MACRO(num, "Odd");
    else
        MACRO(num, "Even");

    return 0;
}
```

编译并运行上面的代码，现在这段代码可以正常工作了。

```cpp
[narendra@/media/partition/GFG]$ make macro
cc     macro.c   -o macro
[narendra@/media/partition/GFG]$ ./macro 
Enter a number: 9
9 is Odd number
[narendra@/media/partition/GFG]$ ./macro 
Enter a number: 10
10 is Even number
[narendra@/media/partition/GFG]$ 

```

我们在“do–while(0)”循环中包含了宏，在 while 结束时，我们将条件设置为“while(0)”，这就是为什么这个循环只执行一次。

类似地，我们可以用括号将多行宏括起来，而不是“do–while(0)”循环。通过使用这个技巧，我们可以达到同样的效果。让我们看看例子。

```cpp
#include <stdio.h>

#define MACRO(num, str) ({\
            printf("%d", num);\
            printf(" is");\
            printf(" %s number", str);\
            printf("\n");\
           })

int main(void)
{
    int num;

    printf("Enter a number: ");
    scanf("%d", &num);

    if (num & 1)
        MACRO(num, "Odd");
    else
        MACRO(num, "Even");

    return 0;
}
```

```cpp
[narendra@/media/partition/GFG]$ make macro
cc     macro.c   -o macro
[narendra@/media/partition/GFG]$ ./macro 
Enter a number: 10
10 is Even number
[narendra@/media/partition/GFG]$ ./macro 
Enter a number: 15
15 is Odd number
[narendra@/media/partition/GFG]$ 

```

本文由**纳伦德拉·康拉尔卡尔**整理。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。