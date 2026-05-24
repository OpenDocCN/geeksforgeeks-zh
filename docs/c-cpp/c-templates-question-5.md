# C++ |模板|问题 5

> 原文:[https://www.geeksforgeeks.org/c-templates-question-5/](https://www.geeksforgeeks.org/c-templates-question-5/)

以下程序的输出？假设 char 的大小是 1 字节，int 的大小是 4 字节，编译器没有进行对齐。

```cpp
#include<iostream>
#include<stdlib.h>
using namespace std;

template<class T, class U>
class A  {
    T x;
    U y;
    static int count;
};

int main()  {
   A<char, char> a;
   A<int, int> b;
   cout << sizeof(a) << endl;
   cout << sizeof(b) << endl;
   return 0;
}
```

**(甲)**

```cpp
6
12
```

**(B)**

```cpp
2
8
```

**(C)** 编译器错误:不能有多个模板参数。
**(四)**

```cpp
8
8
```

**回答:** **(B)**

**说明:**由于计数是静态的，所以不计入 sizeof。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)