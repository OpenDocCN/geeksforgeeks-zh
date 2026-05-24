# C++ |模板|问题 6

> 原文:[https://www.geeksforgeeks.org/c-templates-question-6/](https://www.geeksforgeeks.org/c-templates-question-6/)

以下程序的输出？假设 int 的大小是 4 字节，double 的大小是 8 字节，编译器没有进行对齐。

```cpp
#include<iostream>
#include<stdlib.h>
using namespace std;

template<class T, class U, class V=double>
class A  {
    T x;
    U y;
    V z;
    static int count;
};

int main()
{
   A<int, int> a;
   A<double, double> b;
   cout << sizeof(a) << endl;
   cout << sizeof(b) << endl;
   return 0;
}
```

**(甲)**

```cpp
16
24
```

**(B)**

```cpp
8
16
```

**(C)**

```cpp
20
28
```

**(D)** 编译器错误:模板参数不能有默认值。

**回答:** **(A)**

**说明:**模板也可以有默认参数。规则是一样的，所有默认值都必须在最右边。

因为计数是静态的，所以它不计入 sizeof。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)