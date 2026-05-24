# C++ |模板|问题 2

> 原文:[https://www.geeksforgeeks.org/c-templates-question-2/](https://www.geeksforgeeks.org/c-templates-question-2/)

预测产量？

```cpp
#include <iostream>
using namespace std;

template <typename T>
void fun(const T&x)
{
    static int count = 0;
    cout << "x = " << x << " count = " << count << endl;
    ++ count;
    return;
}

int main()
{
    fun<int> (1); 
    cout << endl;
    fun<int>(1); 
    cout << endl;
    fun<double>(1.1);
    cout << endl;
    return 0;
}
```

**(甲)**

```cpp
x = 1 count = 0

x = 1 count = 1

x = 1.1 count = 0
```

**(B)**

```cpp
x = 1 count = 0

x = 1 count = 0

x = 1.1 count = 0
```

**(C)**

```cpp
x = 1 count = 0

x = 1 count = 1

x = 1.1 count = 2
```

**(D)** 编译器错误

**答案:** **(A)**

**解释:**编译器为每个数据类型创建一个模板函数的新实例。所以编译器在上面的例子中创建了两个函数，一个用于 int，另一个用于 double。每个实例都有自己的静态变量副本。函数的 int 实例被调用了两次，因此第二次调用的 count 会递增。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)