# 是 C++ 中的 _ 多态模板

> 原文:[https://www.geeksforgeeks.org/is_polymorphic-template-in-c/](https://www.geeksforgeeks.org/is_polymorphic-template-in-c/)

C++ STL 的**STD::is _ 多态模板**用于检查类型是否为多态类类型。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template < class T > struct is_polymorphic;

```

**参数**:此模板包含单参数 **T (Trait 类)**检查 T 是否为多态类类型。

**返回值**:该模板返回如下所示的布尔值:

*   **True** :如果类型是多态类。
*   **False** :如果类型是非多态类。

下面的程序说明了 C++ STL 中的标准::is _ 多态模板:

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_polymorphic template

#include <iostream>
#include <type_traits>
using namespace std;

struct gfg {
    virtual void foo();
};

struct geeks : gfg {
};

class raj {
    virtual void foo() = 0;
};

struct sam : raj {
};

int main()
{
    cout << boolalpha;
    cout << "is_polymorphic:"
         << '\n';
    cout << "gfg:"
         << is_polymorphic<gfg>::value
         << '\n';
    cout << "geeks:"
         << is_polymorphic<geeks>::value
         << '\n';
    cout << "raj:"
         << is_polymorphic<raj>::value
         << '\n';
    cout << "sam:"
         << is_polymorphic<sam>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_polymorphic:
gfg:true
geeks:true
raj:true
sam:true

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_polymorphic template

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
    cout << "is_polymorphic:"
         << '\n';
    cout << "gfg:"
         << is_polymorphic<gfg>::value
         << '\n';
    cout << "sam:"
         << is_polymorphic<sam>::value
         << '\n';
    cout << "raj:"
         << is_polymorphic<raj>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_polymorphic:
gfg:false
sam:true
raj:true

```