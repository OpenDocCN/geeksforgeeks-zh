# 是 C++ 中的 _ reference Template

> 原文:[https://www.geeksforgeeks.org/is_reference-template-in-c/](https://www.geeksforgeeks.org/is_reference-template-in-c/)

C++ STL 的 **std::is_reference 模板**用于检查类型是否为引用类型。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template <class T > struct is_reference;
```

**参数**:本模板接受单个参数 **T(性状类)**，检查 T 是否为参照类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是引用类型。
*   **False** :如果类型是非引用类型。

下面的程序说明了 C++ STL 中的标准::is_reference 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_reference template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
class gfg {
};

int main()
{
    cout << boolalpha;
    cout << "is_reference: "
         << '\n';
    cout << "gfg: "
         << is_reference<gfg>::value
         << '\n';
    cout << "gfg&: "
         << is_reference<gfg&>::value
         << '\n';
    cout << "gfg&&: "
         << is_reference<gfg&&>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_reference: 
gfg: false
gfg&: true
gfg&&: true

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_reference template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_reference: "
         << '\n';
    cout << "int: "
         << is_reference<int>::value
         << '\n';
    cout << "int&: "
         << is_reference<int&>::value
         << '\n';
    cout << "int&&: "
         << is_reference<int&&>::value
         << '\n';
    cout << "char: "
         << is_reference<char>::value
         << '\n';
    cout << "char&: "
         << is_reference<char&>::value
         << '\n';
    cout << "char&&: "
         << is_reference<char&&>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_reference: 
int: false
int&: true
int&&: true
char: false
char&: true
char&&: true

```

**程序 3** :

```cpp
// C++ program to illustrate
// std::is_reference template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{

    cout << boolalpha;
    cout << "is_reference: "
         << '\n';
    cout << "float: "
         << is_reference<float>::value
         << '\n';
    cout << "float&: "
         << is_reference<float&>::value
         << '\n';
    cout << "float&&: "
         << is_reference<float&&>::value
         << '\n';
    cout << "double: "
         << is_reference<double>::value
         << '\n';
    cout << "double&: "
         << is_reference<double&>::value
         << '\n';
    cout << "double&&: "
         << is_reference<double&&>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_reference: 
float: false
float&: true
float&&: true
double: false
double&: true
double&&: true

```