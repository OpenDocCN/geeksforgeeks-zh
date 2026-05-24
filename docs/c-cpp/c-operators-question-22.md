# C |操作员|第 22 题

> 原文:[https://www.geeksforgeeks.org/c-operators-question-22/](https://www.geeksforgeeks.org/c-operators-question-22/)

```cpp
#include<stdio.h>
int main()
{
  int a = 2,b = 5;
  a = a^b;
  b = b^a;
  printf("%d %d",a,b);
  return 0;
}
```

**(a)**5 2
**(b)**2 5
**(c)**7
**(d)**7 2

**答案:****(d)**

**解释:** ^是按位异或运算符。

a = 2 (10)
b = 5 (101)

a = a^b(10 ^ 101)= 7(111)
b = a^b(111 ^ 101)= 2(10)

[本题竞猜](https://www.geeksforgeeks.org/c-language-2-gq/operators-gq/)