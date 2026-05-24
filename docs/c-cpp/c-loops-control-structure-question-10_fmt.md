# C |循环&控制结构|问题 10

> 原文: [https://www.geeksforgeeks.org/c-loops-control-structure-question-10/](https://www.geeksforgeeks.org/c-loops-control-structure-question-10/)

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
     printf("%d  ", i);
   }
   return 0;
}
```

**(A)** 5 10 15 20
**(B)** 7 12 17 22
**(C)** 16 21
**(D)** 编译器错误

**答案:** `(C)`

**解释:** 最初 `i = 0`。因为 `case 0` 为真，所以 `i` 变成了 5，因为在 `switch` 块的最后一个语句之前没有 `break` 语句，所以 `i` 变成了 16。现在在下一次迭代中，没有一个 `case` 是真的，所以执行变成了 `default`，`i` 变成了 21。
在 C 语言中，如果一种 `case` 为真，则执行 `switch` 块，直到找到 `break` 语句。如果没有 `break` 语句，所有 `case` 都在为真的 `case` 之后执行。如果您想知道为什么像这样实现 `switch`，那么这种实现对于下面这样的情况很有用。

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