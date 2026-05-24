# C++ | Misc C++ |问题 2

> 原文:[https://www.geeksforgeeks.org/c-misc-c-question-2/](https://www.geeksforgeeks.org/c-misc-c-question-2/)

```cpp
#include<iostream>
using namespace std;
int x = 1;
void fun()
{
    int x = 2;
    {
        int x = 3;
        cout << ::x << endl;
    }
}
int main()
{
    fun();
    return 0;
}
```

**(A)**1
**(B)**2
**(C)**3
**(D)**0

**答案:****(A)**

**说明:**x 的值为 1。

范围解析运算符与变量名一起使用时，总是引用全局变量。

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/misc-c-gq/)