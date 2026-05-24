# C++ |运算符重载|问题 7

> 原文:[https://www . geesforgeks . org/c-operator-overload-question-7/](https://www.geeksforgeeks.org/c-operator-overloading-question-7/)

以下程序的输出？

```cpp
#include <iostream>
using namespace std;
class Test2
{
    int y;
};

class Test
{
    int x;
    Test2 t2;
public:
    operator Test2 ()  { return t2; }
    operator int () { return x; }
};

void fun ( int x) { cout << "fun(int) called"; }
void fun ( Test2 t ) { cout << "fun(Test 2) called"; }

int main()
{
    Test t;
    fun(t);
    return 0;
}
```

**(A)** fun(int)叫
**(B)** fun(Test 2)叫
**(C)** 编译器错误:模棱两可地叫 fun()

**答案:****(C)**

**解释:**类 Test 有两个转换运算符重载，int 和 Test 2。int 和 Test2 有两个有趣的地方。

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)