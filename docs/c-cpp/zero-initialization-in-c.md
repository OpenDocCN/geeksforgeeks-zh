# c++ 中的零初始化

> 原文:[https://www.geeksforgeeks.org/zero-initialization-in-c/](https://www.geeksforgeeks.org/zero-initialization-in-c/)

将对象的初始值设置为零称为*零初始化。*
**语法** :

```cpp
static T object;

Tt = {} ;

T {} ;

char array [n] = " ";
```

零初始化在以下情况下执行:-

1.  在任何其他初始化之前，对于每个具有静态或线程本地存储持续时间的命名变量，零被初始化，该变量不经历常数初始化(从 C++ 14 开始)。
2.  对于非类类型和没有构造函数的值初始化类类型的成员，零被初始化为值初始化序列的一部分。
3.  当用非常短的字符串初始化字符数组时，数组的剩余部分被零初始化。

零初始化的效果是:

*   如果 T 是标量类型，则对象被初始化为通过将整数文字 0 转换为 T 而获得的值
*   如果 T 是非联合类类型，则每个非静态数据成员和每个基类子对象被零初始化，填充被初始化为零位。
*   如果 T 是联合类型，则对象的第一个非静态命名数据成员被初始化为零，填充被初始化为零位。
*   如果 T 是数组类型，则每个数组元素都是零初始化的。
*   如果 T 是引用类型，则不执行初始化。

**要点** :

*   静态变量和线程局部变量首先被零初始化，然后按照程序中的指定再次初始化，例如，在程序启动时，函数局部静态变量首先被零初始化，然后在第一次输入函数时调用其构造函数。如果没有用于声明非类静态的初始值设定项，那么默认初始化什么也不做，保持早期零初始化的结果不变。
*   零初始化的指针称为空指针，即使空指针的值不是整数零。

下面程序举例说明了 C++ 中的零初始化:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate zero initialization

#include <iostream>
#include <string>

struct foo {
    int x, y, z;
};

double f[3]; // zero-initialized to three 0.0's

int* p; // zero-initialized to null pointer value

// zero-initialized to indeterminate value
// then default-initialized to ""
std::string s;

int main(int argc, char* argv[])
{
    foo x = foo();

    std::cout << x.x << x.y << x.z << '\n';

    return 0;
}
```

**Output:** 

```cpp
000
```

**参考**:[https://en . cppreference . com/w/CPP/language/zero _ initiation](https://en.cppreference.com/w/cpp/language/zero_initialization)T4】