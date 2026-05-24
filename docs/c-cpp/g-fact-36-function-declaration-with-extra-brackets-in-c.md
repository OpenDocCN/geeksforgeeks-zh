# C/c++ 中带有函数名的额外括号

> 原文:[https://www . geesforgeks . org/g-fact-36-function-declaration-带括号外-in-c/](https://www.geeksforgeeks.org/g-fact-36-function-declaration-with-extra-brackets-in-c/)

考虑下面的 C 程序。程序在函数名周围有额外的括号。

```cpp
// C program to show that extra brackets with function
// name work
#include <stdio.h>

void (foo)(int n)
{
   printf("Function : %d ", n);
}

int main()
{
   (foo)(4);
   return 0;  
}
```

输出:

```cpp
Function 4
```

所以在 C/C++ 中用函数名加上额外的括号是有效的。

**它有什么用？**
一个用法可能是，如果我们有一个与函数同名的宏，那么多余的括号可以避免在我们想要调用函数的地方进行宏扩展。

```cpp
// C program to show that extra brackets with function
// name can be useful if we have a macro with same name
#include <stdio.h>
#define foo(n)  printf("\nMacro : %d ", n);

void (foo)(int n)
{
   printf("Function : %d ", n);
}

int main()
{
   (foo)(4);
   foo(4);
   return 0;
}
```

输出:

```cpp
Function 4
Macro : 4
```

如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论