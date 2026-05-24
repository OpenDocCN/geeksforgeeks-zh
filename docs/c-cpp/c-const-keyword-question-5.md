# C++ | const 关键字|问题 5

> 原文:[https://www.geeksforgeeks.org/c-const-keyword-question-5/](https://www.geeksforgeeks.org/c-const-keyword-question-5/)

C++ 程序的输出？

```cpp
#include <iostream>
int const s=9;
int main()
{
    std::cout << s;
    return 0;
}
```

由**Pravasi Meet**
**(A)**9
**(B)**编译器错误

**答案:****(A)**

**解释:**以上程序编译&运行良好。Const 关键字可以放在变量类型之后或变量类型之前。但是大多数程序员更喜欢把 const 关键字放在变量类型之前。

[本题小测验](https://www.geeksforgeeks.org/c-plus-plus-gq/const-keyword-gq/)