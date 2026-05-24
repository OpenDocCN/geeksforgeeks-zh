# 当后面有 fgets()/get()/scanf()时，scanf()有问题

> 原文:[https://www . geesforgeks . org/problem-with-scanf-what-is-fgetsgetsscanf-after-it/](https://www.geeksforgeeks.org/problem-with-scanf-when-there-is-fgetsgetsscanf-after-it/)

考虑下面用 c 语言编写的简单程序。该程序使用 scanf()读取一个整数，然后使用 fgets()读取一个字符串。

```cpp
// C program to demonstrate the problem when
// fgets()/gets() is used after scanf()
#include<stdio.h>

int main()
{
   int x;
   char str[100];
   scanf("%d", &x);
   fgets(str, 100, stdin);
   printf("x = %d, str = %s", x, str);
   return 0;
}
```

输入

```cpp
10
test
```

输出:

```cpp
x = 10, str =  
```

上面代码的问题是 scanf()读取一个整数，并在缓冲区中留下一个换行符。所以 fgets()只读取换行符，字符串“test”被程序忽略。

在循环中使用 scanf()时，也会出现类似的问题。

```cpp
// C program to demonstrate the problem when
// scanf() is used in a loop
#include<stdio.h>

int main()
{
    char c;
    printf("......Enter q to quit......\n");
    do
    {
        printf("Enter a character\n");
        scanf("%c", &c);
        printf("%c\n", c);
    }
    while (c != 'q');
    return 0;
}
```

输入

```cpp
a
b
q
```

输出:

```cpp
......Enter q to quit......
Enter a character
a
Enter a character

Enter a character
b
Enter a character

Enter a character
q
```

我们可以注意到，上面的程序打印了一个额外的“输入一个字符”，后跟一个额外的新行。这是因为每个 scanf()都会在缓冲区中留下一个换行符，供下一个 scanf 读取。

**如何解决以上问题？**

1.  We can make scanf () read new rows by using extra "\n", namely **scanf ("%d \ n", & x)** . Actually, **scanf ("%d", & x)** can also be used (pay attention to extra space).
2.  We can add a getchar () after scanf () to read extra line breaks.

**修正程序见[本](https://ide.geeksforgeeks.org/nnfP2h)和[本](https://ide.geeksforgeeks.org/BAD6dR)。**

当在 nextXXX() 之后使用 nextLine()时，Java 中的 Scanner 也会出现同样的[问题。](https://www.geeksforgeeks.org/difference-between-scanner-and-bufferreader-class-in-java/)

本文由 **Dheeraj Gupta** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论