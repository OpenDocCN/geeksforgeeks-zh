# C++ 中的 `is_abstract` 模板

> 原文：`https://www.geeksforgeeks.org/is_abstract-template-in-c/`

C++ STL 的 `std::is_abstract` 模板用于检查类型是否为抽象类类型。它返回一个布尔值来显示检查结果。

**语法**：

```cpp
template <class T> struct is_abstract;
```

**参数**：此模板包含单参数 `T`（Trait 类），检查 `T` 是否为抽象类类型。

**返回值**：该模板返回如下所示的布尔值：

*   **True**：如果类型是抽象类。
*   **False**：如果类型是非抽象类。

下面的程序说明了 C++ STL 中的 `std::is_abstract` 模板：

**程序 1**：

```cpp
// C++ program to illustrate
// std::is_abstract template

#include <iostream>
#include <type_traits>
using namespace std;

struct gfg {
    int m;
};

struct sam {
    virtual void foo() = 0;
};

class raj : sam {
};

int main()
{
    cout << boolalpha;
    cout << "is_abstract:" << '\n';
    cout << "gfg:" << is_abstract<gfg>::value << '\n';
    cout << "sam:" << is_abstract<sam>::value << '\n';
    cout << "raj:" << is_abstract<raj>::value << '\n';
    return 0;
}
```

**程序 2**：

```cpp
// C++ program to illustrate
// std::is_abstract template

#include <iostream>
#include <type_traits>
using namespace std;

struct gfg {
    virtual void foo();
};

class raj {
    virtual void foo() = 0;
};

struct sam : raj {
};

class geek {
    virtual void foo();
};

int main()
{
    cout << std::boolalpha;
    cout << "is_abstract:" << '\n';
    cout << "gfg:" << is_abstract<gfg>::value << '\n';
    cout << "raj:" << is_abstract<raj>::value << '\n';
    cout << "sam:" << is_abstract<sam>::value << '\n';
    cout << "geek:" << is_abstract<geek>::value << '\n';

    return 0;
}
```