# C |存储类和类型限定符|问题 11

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-11/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-11/)

考虑下面的 C 函数

```cpp
int f(int n) 
{ 
   static int i = 1; 
   if (n >= 5) 
      return n; 
   n = n+i; 
   i++ ; 
   return f(n); 
}
```

f(1)返回的值是(GATE CS 2004)

**(A)**5
**(B)**6
**(C)**7
**(D)**8

**回答:****(C)**

**说明:**既然我是静态的，第一行 f()只执行一次。

```cpp
Execution of f(1)
    i = 1
    n = 2
    i = 2
 Call f(2)
    i = 2
    n = 4
    i = 3
 Call f(4)
   i = 3
   n = 7
   i = 4
 Call f(7)
  since n >= 5 return n(7)
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)