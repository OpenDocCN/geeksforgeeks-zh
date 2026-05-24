# C |宏&预处理器|问题 7

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-7/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-7/)

输出？

```cpp
# include <stdio.h>
# define scanf  "%s Geeks Quiz "
int main()
{
   printf(scanf, scanf);
   return 0;
}
```

**(A)** 编译器错误
**(B)** %s 极客小测验
**(C)** 极客小测验
**(D)** %s 极客小测验极客小测验

**答案:****(D)**

**说明:**经过编译预处理阶段后，printf 语句将变为。
printf("%s 极客小测验"、" %s 极客小测验")；
现在你很容易猜到为什么输出是“%s 极客问答极客问答”。