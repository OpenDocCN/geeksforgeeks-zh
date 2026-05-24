# C |功能|问题 5

> 原文:[https://www.geeksforgeeks.org/c-functions-question-5/](https://www.geeksforgeeks.org/c-functions-question-5/)

输出？

```cpp
#include <stdio.h>

int main()
{
    int (*ptr)(int ) = fun;
    (*ptr)(3);
    return 0;
}

int fun(int n)
{
  for(;n > 0; n--)
    printf("GeeksQuiz ");
  return 0;
}
```

**(A)**geek squiz geek squiz
**(B)**geek squiz geek squiz
**(C)**编译器错误
**(D)** 运行时错误

**答案:****(C)**

**解释:**程序唯一的问题是 ***好玩**以下程序运行良好，并打印出“极客 sQuiz 极客 sQuiz”*

```cpp
int fun(int n);

int main()
{
    // ptr is a pointer to function fun()
    int (*ptr)(int ) = fun;

    // fun() called using pointer 
    (*ptr)(3);
    return 0;
}

int fun(int n)
{
  for(;n > 0; n--)
    printf("GeeksQuiz ");
}

```

[本题小考](https://www.geeksforgeeks.org/functions-properties-and-types-injective-surjective-bijective/)