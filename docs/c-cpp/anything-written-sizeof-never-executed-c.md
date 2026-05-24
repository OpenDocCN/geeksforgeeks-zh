# 用 sizeof()写的任何东西都不会在 C

中执行

> 原文:[https://www . geesforgeks . org/any-writed-sizeof-never-executed-c/](https://www.geeksforgeeks.org/anything-written-sizeof-never-executed-c/)

在 C/C++ 中，sizeof()运算符用于查找日期类型或变量的大小。从不执行用 sizeof()编写的表达式。

示例:

```cpp
// C program to demonstrate that the
// expressions written in sizeof() are
// never executed
#include <stdio.h>

int main(){

    // The printf in sizeof is not executed
    // Only the return type of printf is 
    // considered and its size is evaluated
    // by sizeof,
    int a = sizeof(printf("hey"));

    printf("%d", a);

    return 0;
}
```

```cpp
Output:
4

```

即使我们在 sizeof()中指定了一个值，这些更改也不会得到反映。

```cpp
// One more C program to demonstrate that 
// the expressions written in sizeof() are
// never executed
#include <stdio.h>

int main() {
    int a = 5;
    int b = sizeof(a = 6);
    printf("a = %d,  b = %d\n", a, b);
    return 0;
}
```

```cpp
Output:
a = 5, b = 4

```

本文由**尼舒辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。