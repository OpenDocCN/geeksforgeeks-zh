# 是 C++ 中的 _ lvalue _ reference Template

> 原文:[https://www . geesforgeks . org/is _ lvalue _ reference-template-in-CPP/](https://www.geeksforgeeks.org/is_lvalue_reference-template-in-cpp/)

C++ STL 的 **std::is_lvalue_reference 模板**用于检查类型是否为 lvalue 引用类型。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template <class T > struct is_lvalue_reference;
```

**模板参数**:该模板接受单个参数 **T(性状类)**，检查 T 是否为左值引用类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是左值引用。
*   **False** :如果类型是非左值引用。

下面的程序说明了 C++ STL 中的标准::is_lvalue_reference 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_lvalue_reference template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
class gfg {
};

int main()
{
    cout << std::boolalpha;
    cout << "is_lvalue_reference: "
         << '\n';
    cout << "gfg: "
         << is_lvalue_reference<gfg>::value
         << '\n';
    cout << "gfg&: "
         << is_lvalue_reference<gfg&>::value
         << '\n';
    cout << "gfg&&: "
         << is_lvalue_reference<gfg&&>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_lvalue_reference: 
gfg: false
gfg&: true
gfg&&: false

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_lvalue_reference template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{

    cout << boolalpha;
    cout << "is_lvalue_reference: "
         << '\n';
    cout << "int: "
         << is_lvalue_reference<int>::value
         << '\n';
    cout << "int&: "
         << is_lvalue_reference<int&>::value
         << '\n';
    cout << "int&&: "
         << is_lvalue_reference<int&&>::value
         << '\n';
    cout << "char: "
         << is_lvalue_reference<char>::value
         << '\n';
    cout << "char&: "
         << is_lvalue_reference<char&>::value
         << '\n';
    cout << "char&&: "
         << is_lvalue_reference<char&&>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_lvalue_reference: 
int: false
int&: true
int&&: false
char: false
char&: true
char&&: false

```

**程序 3** :

```cpp
// C++ program to illustrate
// std::is_lvalue_reference template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{

    cout << boolalpha;
    cout << "is_lvalue_reference: "
         << '\n';
    cout << "float: "
         << is_lvalue_reference<float>::value
         << '\n';
    cout << "float&: "
         << is_lvalue_reference<float&>::value
         << '\n';
    cout << "float&&: "
         << is_lvalue_reference<float&&>::value
         << '\n';
    cout << "double: "
         << is_lvalue_reference<double>::value
         << '\n';
    cout << "double&: "
         << is_lvalue_reference<double&>::value
         << '\n';
    cout << "double&&: "
         << is_lvalue_reference<double&&>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_lvalue_reference: 
float: false
float&: true
float&&: false
double: false
double&: true
double&&: false

```