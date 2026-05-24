# C++ |构造函数|第 16 题

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-16/](https://www.geeksforgeeks.org/c-constructors-question-16/)

预测后续程序的输出？

```cpp
#include <iostream>
using namespace std;
class Test
{
private:
    int x;
public:
    Test(int i)
    {
        x = i;
        cout << "Called" << endl;
    }
};

int main()
{
    Test t(20);
    t = 30; // conversion constructor is called here.
    return 0;
}
```

**(A)** 编译错误
**(B)**

```cpp
Called
Called
```

**(C)**

```cpp
Called
```

**回答:** **(B)**

**说明:**如果一个类有一个可以用单个参数调用的构造函数，那么这个构造函数就变成了转换构造函数，因为这样的构造函数允许自动转换到正在构造的类。

当单一引数的类型指派给物件时，可以在任何地方呼叫转换建构函式。给定程序的输出是

```cpp
Called
Called
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)