# C |循环&控制结构|问题 10

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-10/](https://www.geeksforgeeks.org/c-loops-control-structure-question-10/)

```cpp
# include <stdio.h>
int main()
{
   int i = 0;
   for (i=0; i<20; i++)
   {
     switch(i)
     {
       case 0:
         i += 5;
       case 1:
         i += 2;
       case 5:
         i += 5;
       default:
         i += 4;
         break;
     }
     printf("%d  ", i);
   }
   return 0;
}
```

**(A)**5 10 15 20
**(B)**7 12 17 22
**(C)**16 21
**(D)**编译器错误

**答案:****(C)**

**解释:**最初 i = 0。因为情况 0 为真，所以我变成了 5，因为在开关块的最后一个语句之前没有 break 语句，所以我变成了 16。现在在下一次迭代中，没有一个案例是真的，所以执行变成了默认，我变成了 21。
在 C 语言中，如果一种情况为真，则执行开关块，直到找到 break 语句。如果没有 break 语句，所有案例都在真正的案例之后执行。如果您想知道为什么像这样实现 switch，那么这种实现对于下面这样的情况很有用。

```cpp
 switch (c)
 {
    case 'a':
    case 'e':
    case 'i' :
    case 'o':
    case 'u':
      printf(" Vowel character");
      break;
    default :
      printf("Not a Vowel character");; break;
  }
```