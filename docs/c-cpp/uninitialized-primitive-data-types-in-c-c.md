# C/c++ 中未初始化的原语数据类型

> 原文:[https://www . geesforgeks . org/uninitialized-primitive-data-type-in-c-c/](https://www.geeksforgeeks.org/uninitialized-primitive-data-types-in-c-c/)

**你认为使用未初始化的原语数据类型会发生什么？**
你可以假设编译器应该给你的基元类型变量分配有意义的值，比如 0 代表 int，0.0 代表 float。char 数据类型呢？

让我们通过在集成开发环境中运行代码来找到答案。

```cpp
#include <iostream>

using namespace std;

int main()
{
    // The following primitive data type variables will not
    // be initialized with any default values
    char ch;
    float f;
    int i;
    double d;
    long l;

    cout << ch << endl;
    cout << f << endl;
    cout << i << endl;
    cout << d << endl;
    cout << l << endl;

    return 0;
}
```

GFGs 集成开发环境中的输出:

```cpp

5.88052e-39
0
6.9529e-310
0

```

Codechef IDE 中的输出:

```cpp

0
0
0
0

```

我机器上的输出:

```cpp

1.4013e-045
0
2.96439e-323
0

```

 **C/c++ 编译器为什么不用默认值初始化变量？**
“保持 C++ 可行性的一个因素是零开销规则:你不用的东西，你不用付钱。”-斯特鲁普。

初始化堆栈变量的开销很高，因为这会妨碍执行速度，因此这些变量可能包含不确定的值。在代码中使用基元数据类型变量之前，对其进行初始化被认为是最佳实践。