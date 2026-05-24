# 是 C++ 中的 _ rvalue _ reference Template

> 原文:[https://www . geesforgeks . org/is _ rvalue _ reference-template-in-CPP/](https://www.geeksforgeeks.org/is_rvalue_reference-template-in-cpp/)

C++ STL 的 **std::is_rvalue_reference 模板**用于检查类型是否为 rvalue 引用类型。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template <class T > struct is_rvalue_reference;
```

**参数**:本模板接受单个参数 **T(性状类)**，检查 T 是否为右值参照类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是右值 _ 引用类型。
*   **False** :如果类型是非右值 _ 引用类型。

下面的程序说明了 C++ STL 中的标准::is_lvalue_reference 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_rvalue_reference template

#include <iostream>
#include <type_traits>
using namespace std;

// main program

class gfg {
};

int main()
{
    cout << std::boolalpha;
    cout << "is_rvalue_reference: "
         << '\n';
    cout << "gfg: "
         << is_rvalue_reference<gfg>::value
         << '\n';
    cout << "gfg&: "
         << is_rvalue_reference<gfg&>::value
         << '\n';
    cout << "gfg&&: "
         << is_rvalue_reference<gfg&&>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_rvalue_reference: 
gfg: false
gfg&: false
gfg&&: true

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_rvalue_reference template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{

    cout << std::boolalpha;
    cout << "is_rvalue_reference: "
         << '\n';
    cout << "int: "
         << is_rvalue_reference<int>::value
         << '\n';
    cout << "int&: "
         << is_rvalue_reference<int&>::value
         << '\n';
    cout << "int&&: "
         << is_rvalue_reference<int&&>::value
         << '\n';
    cout << "char: "
         << is_rvalue_reference<char>::value
         << '\n';
    cout << "char&: "
         << is_rvalue_reference<char&>::value
         << '\n';
    cout << "char&&: "
         << is_rvalue_reference<char&&>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_rvalue_reference: 
int: false
int&: false
int&&: true
char: false
char&: false
char&&: true

```

**程序 3** :

```cpp
// C++ program to illustrate
// std::is_rvalue_reference template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << std::boolalpha;
    cout << "is_rvalue_reference: "
         << '\n';
    cout << "float: "
         << is_rvalue_reference<float>::value
         << '\n';
    cout << "float&: "
         << is_rvalue_reference<float&>::value
         << '\n';
    cout << "float&&: "
         << is_rvalue_reference<float&&>::value
         << '\n';
    cout << "double: "
         << is_rvalue_reference<double>::value
         << '\n';
    cout << "double&: "
         << is_rvalue_reference<double&>::value
         << '\n';
    cout << "double&&: "
         << is_rvalue_reference<double&&>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_rvalue_reference: 
float: false
float&: false
float&&: true
double: false
double&: false
double&&: true

```