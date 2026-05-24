# C++ | const 关键字|问题 1

> 原文:[https://www.geeksforgeeks.org/c-const-keyword-question-1/](https://www.geeksforgeeks.org/c-const-keyword-question-1/)

预测以下程序的输出

```cpp
#include <iostream>
using namespace std;
int main()
{
    const char* p = "12345";
    const char **q = &p;
    *q = "abcde";
    const char *s = ++ p;
    p = "XYZWVU";
    cout << *++ s;
    return 0;
}
```

**(A)** 编译器错误
**(B)**C
**(C)**B
**(D)**垃圾值

**答案:****(B)**

**解释:**输出为‘C’

const char* p = "12345 "声明一个指向常量的指针。所以我们不能给 p 赋值，但是我们可以给 p 赋值。

const char **q = &p;声明一个指向指针的指针。我们不能给**q 赋值，但是我们可以给 q 和*q 赋值。

* q = " abcde 将 p 改为指向“abcde”

const char * s =++ p；将文字“bcde”的地址分配给 s。同样，不能为*s 分配新值，但可以更改 s。

语句 printf("%cn "，*++ s)将 s 更改为" cde "，并打印 s 处的第一个字符。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)