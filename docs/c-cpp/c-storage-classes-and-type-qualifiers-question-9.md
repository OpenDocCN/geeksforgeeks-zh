# C |存储类和类型限定符|问题 9

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-9/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-9/)

输出？

```cpp
#include <stdio.h>
int fun()
{
  static int num = 16;
  return num--;
}

int main()
{
  for(fun(); fun(); fun())
    printf("%d ", fun());
  return 0;
}
```

**(A)** 无限循环
**(B)**13 10 7 4 1
**(C)**14 11 8 5 2
**(D)**15 12 8 5 2

**答案:****(C)**

**解释:**自*数*为静中此外，由于语句 return*num*–是后缀，因此它会返回 *num* 的旧值，并为下一次函数调用更新该值。

```cpp
fun() called first time: num = 16 // for loop initialization done;

In test condition, compiler checks for non zero value

fun() called again : num = 15

printf("%d \n", fun());:num=14 ->printed

Increment/decrement condition check

fun(); called again : num = 13

----------------

fun() called second time: num: 13 

In test condition,compiler checks for non zero value

fun() called again : num = 12

printf("%d \n", fun());:num=11 ->printed

fun(); called again : num = 10

--------

fun() called second time : num = 10 

In test condition,compiler checks for non zero value

fun() called again : num = 9

printf("%d \n", fun());:num=8 ->printed

fun(); called again   : num = 7

--------------------------------

fun() called second time: num = 7

In test condition,compiler checks for non zero value

fun() called again : num = 6

printf("%d \n", fun());:num=5 ->printed

fun(); called again   : num = 4

-----------

fun() called second time: num: 4 

In test condition,compiler checks for non zero value

fun() called again : num = 3

printf("%d \n", fun());:num=2 ->printed

fun(); called again   : num = 1

----------

fun() called second time: num: 1 

In test condition,compiler checks for non zero value

fun() called again : num = 0 => STOP 
```

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/storage-classes-gq/)