# 是 C++ 中的 _standard_layout 模板

> 原文:[https://www . geesforgeks . org/is _ standard _ layout-template-in-c/](https://www.geeksforgeeks.org/is_standard_layout-template-in-c/)

C++ STL 的 **std::is_standard_layout 模板**用于检查类型是否为标准布局。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template < class T > struct is_standard_layout;

```

**参数**:此模板包含单参数 **T (Trait 类)**检查 T 是否为标准布局类型。

**返回值**:该模板返回如下所示的布尔值:

*   **True** :如果类型是标准布局类型。
*   **False** :如果类型是非标准布局类型。

下面的程序说明了 C++ STL 中的标准布局模板:

**程序 1** :结构、类和联合相结合。

```cpp
// C++ program to illustrate
// std::is_standard_layout  template

#include <iostream>
#include <type_traits>
using namespace std;

// Class with local variable
class gfg {
    int variab;
};

// Structure with local variable
struct sam {
    int variab;

private:
    int variab_priv;
};

// Empty union
union raj {
};

// Driver code
int main()
{
    cout << boolalpha;
    cout << "Is gfg class a standard layout: "
         << is_standard_layout<gfg>::value << '\n';
    cout << "Is structure sam a standard layout: "
         << is_standard_layout<sam>::value << '\n';
    cout << "Is union raj a standard layout: "
         << is_standard_layout<raj>::value << '\n';
    cout << "Is datatype char a standard layout: "
         << is_standard_layout<char>::value << '\n';
    cout << "Is integer array 'int a[10]' a standard layout: "
         << is_standard_layout<int[10]>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
Is gfg class a standard layout: true
Is structure sam a standard layout: false
Is union raj a standard layout: true
Is datatype char a standard layout: true
Is integer array 'int a[10]' a standard layout: true

```

**程序 2** :带类

```cpp
// C++ program to illustrate
// std::is_standard_layout  template

#include <iostream>
#include <type_traits>
using namespace std;

// Class with local variable
class gfg {
    int variab;
};

// class with local variable
class sam {
    int variab;

private:
    int variab_priv;
};

// Empty class
class raj {
};

// Driver code
int main()
{
    cout << boolalpha;
    cout << "Is gfg class a standard layout: "
         << is_standard_layout<gfg>::value << '\n';
    cout << "Is structure sam a standard layout: "
         << is_standard_layout<sam>::value << '\n';
    cout << "Is union raj a standard layout: "
         << is_standard_layout<raj>::value << '\n';
    cout << "Is pointer 'int(gfg::*)' a standard layout: "
         << is_standard_layout<int(gfg::*)>::value << '\n';
    cout << "Is pointer 'int *' a standard layout: "
         << is_standard_layout<int*>::value << '\n';
    cout << "Is pointer 'nullptr_t' a standard layout: "
         << is_standard_layout<nullptr_t>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
Is gfg class a standard layout: true
Is structure sam a standard layout: true
Is union raj a standard layout: true
Is pointer 'int(gfg::*)' a standard layout: true
Is pointer 'int *' a standard layout: true
Is pointer 'nullptr_t' a standard layout: true

```