# C++ 中静态函数和常量函数的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-static-and-constant-function-in-cpp/](https://www.geeksforgeeks.org/difference-between-static-and-constant-function-in-cpp/)

[静态函数](https://www.geeksforgeeks.org/what-are-static-functions-in-c/)：是成员函数，仅用于访问[静态数据成员](https://www.geeksforgeeks.org/static-data-members-c/)。它不能访问非静态数据成员，甚至不能调用非静态成员函数。即使不存在该类的对象，也可以调用它。它还用于在类的不同对象之间维护类成员函数的单一副本。

**程序 1:**

### 示例代码

```cpp
// C++ program to illustrate the use
// of static function
#include "bits/stdc++.h"
using namespace std;

class A {
public:
    static void f()
    {
        cout << "GeeksforGeeks!";
    }
};

// Driver Code
int main()
{
    A::f();
}
```

**Output:**

```cpp
GeeksforGeeks!
```

[常量函数](https://www.geeksforgeeks.org/const-member-functions-c/)：是程序中一般声明为常量的函数。它还保证不允许修改对象或调用任何非常量成员函数。它指定函数是只读函数，并且不修改为其调用的对象。

**程序 2:**

### 示例代码

```cpp
// C++ program to illustrate the use
// of const keyword

#include <iostream>
using namespace std;

// Driver Code
int main()
{
    const double a = 1;

    // Using the below line of code
    // gives error
    // a = 2.21;

    cout << a << endl;

    return 0;
}
```

**Output:**

```cpp

```

**静态函数与常量函数的区别:**

| 特性 | 静态函数 | 常量函数 |
| :--- | :--- | :--- |
| 声明方式 | 使用 `static` 关键字声明。 | 使用 `const` 关键字声明。 |
| 修改能力 | 不允许修改变量或数据成员。它被分配到程序的整个生命周期。 | 指定函数是否可以修改对象状态。 |
| 调用方式 | 有助于在不使用类对象的情况下调用函数。 | 有助于避免修改对象。 |
| 调用限制 | 只能由静态数据成员和静态成员函数调用。 | 可以使用任何类型的对象调用。 |
| 主要用途 | 用于声明在程序驻留内存时应更新的全局数据、限制对函数的访问以及在其他文件中重用相同的函数名。 | 用于传递给函数的指针或引用，以避免对对象进行意外更改，并且可以被任何类型的对象调用等。 |
| 本质 | 是成员函数，通常允许使用类来访问函数，而不是使用类的实例。 | 是成员函数，在程序中通常被声明为常量。 |