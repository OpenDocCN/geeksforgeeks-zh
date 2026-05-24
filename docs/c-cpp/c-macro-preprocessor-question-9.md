# C |宏&预处理器|问题 9

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-9/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-9/)

输出？

```cpp
#include<stdio.h> 
#define f(g,g2) g##g2 
int main() 
{ 
   int var12 = 100; 
   printf("%d", f(var,12)); 
   return 0; 
}
```

**(A)** 100
**(B)** 编译器错误
**(C)**0
**(D)**1

**答案:****(A)**

**解释:**运算符##称为“Token-Pasting”或“Merge”运算符。它将两个令牌合并为一个令牌。所以，预处理后，主函数变成如下，打印 100。

```cpp
int main() 
{ 
   int var12 = 100; 
   printf("%d", var12); 
   return 0; 
}
```