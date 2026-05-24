# std 是 C++ 中的 _ object Template

> 原文:[https://www.geeksforgeeks.org/std-is_object-template-in-c/](https://www.geeksforgeeks.org/std-is_object-template-in-c/)

C++ STL 的 **std::is_object 模板**用于检查给定类型是否为对象。它返回一个显示相同内容的布尔值。

**语法:**

```cpp
template <class T > struct is_object;
```

**参数:**该模板接受单个参数 **T (Trait 类)**检查 T 是否为对象类型。

**返回值:**该模板返回如下所示的布尔值:

*   **真**:如果类型是对象。
*   **False** :如果类型是非对象。

下面的程序说明了 C++ STL 中的标准::is_object 模板:

**程序 1:** :

```cpp
// C++ program to illustrate
// std::is_object template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    class gfg {
    };

    cout << boolalpha;
    cout << "is_object:" << endl;
    cout << "sam: " << is_object<gfg>::value << '\n';
    cout << "sam&: " << is_object<gfg&>::value << '\n';
    cout << "int: " << is_object<int>::value << '\n';
    cout << "int&: " << is_object<int&>::value;
    return 0;
}
```

**Output:**

```cpp
is_object:
sam: true
sam&: false
int: true
int&: false

```

**程序 2:** :

```cpp
// C++ program to illustrate
// std::is_object template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    class geeks {
    };

    cout << boolalpha;
    cout << "is_object:" << endl;
    cout << "float: " << is_object<float>::value << '\n';
    cout << "float&: " << is_object<float&>::value << '\n';
    cout << "raj: " << is_object<geeks>::value << '\n';
    cout << "raj&: " << is_object<geeks&>::value << '\n';
    cout << "char: " << is_object<char>::value << '\n';
    cout << "char&: " << is_object<char&>::value;

    return 0;
}
```

**Output:**

```cpp
is_object:
float: true
float&: false
raj: true
raj&: false
char: true
char&: false

```