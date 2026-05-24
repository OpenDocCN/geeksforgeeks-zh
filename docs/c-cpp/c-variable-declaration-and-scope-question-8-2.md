# C |变量声明和范围|问题 8

> 原文:[https://www . geesforgeks . org/c-变量-声明-范围-问题-8-2/](https://www.geeksforgeeks.org/c-variable-declaration-and-scope-question-8-2/)

考虑下面的 C 程序，哪个变量的作用域最长？

```cpp
int a;
int main()
{
   int b;
   // ..
   // ..
}
int c;
```

**(A)**A
**(B)**B
**(C)**C
**(D)**都有相同的范围

**回答:****(A)**

**说明:** a 处处可及。

b 仅限于 main()

c 只有在声明之后才能访问。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/variable-declaration-and-scope-gq/)