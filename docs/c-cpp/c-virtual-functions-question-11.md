# C++ |虚函数|第 11 题

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-11/](https://www.geeksforgeeks.org/c-virtual-functions-question-11/)

静态函数可以是虚拟的吗？下面的程序会编译吗？

```cpp
#include<iostream> 
using namespace std;    

class Test
{
   public:
      virtual static void fun()  { }
};
```

**(A)** 是
**(B)** 否

**回答:** **(B)**

**说明:**静态函数是类特定的，不能在对象上调用。虚函数是根据指向或引用的对象调用的。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)