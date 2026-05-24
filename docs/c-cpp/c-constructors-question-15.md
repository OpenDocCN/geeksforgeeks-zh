# C++ |构造函数|第 15 题

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-15/](https://www.geeksforgeeks.org/c-constructors-question-15/)

```cpp
#include<iostream>
using namespace std;

class Test
{
public:
  Test();
};

Test::Test()  {
    cout << " Constructor Called. ";
}

void fun() {
  static Test t1;
}

int main() {
    cout << " Before fun() called. ";
    fun();
    fun();
    cout << " After fun() called. ";  
    return 0;
}
```

**(一)**建造师调用。fun()调用之前。fun()调用后。
**(B)** 前趣()名曰。已调用构造函数。已调用构造函数。fun()调用后。
**(C)** 前趣()名曰。已调用构造函数。fun()调用后。
**(D)** 构造函数调用。已调用构造函数。fun()调用后。fun()调用之前。

**答案:****(C)**

**说明:**注意在函数`fun()`内，变量`t1`被声明为`static`。因此`Test::Test` 构造函数在程序的生命周期内只被调用一次。
更多信息请参见 C++ 中的 [Static 关键字，阅读“函数中的静态变量”一节](https://www.geeksforgeeks.org/static-keyword-cpp/) [本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)