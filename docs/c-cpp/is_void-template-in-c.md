# 是 C++ 中的 _void 模板

> 原文:[https://www.geeksforgeeks.org/is_void-template-in-c/](https://www.geeksforgeeks.org/is_void-template-in-c/)

C++ STL 的 **std::is_void 模板**用于检查类型是否为空。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template < class T > struct is_void;

```

**参数**:本模板包含单参数 **T(性状类)**检查 T 是否为空型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型为空。
*   **False** :如果类型为非空。

下面的程序说明了 C++ STL 中的标准::is_void 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_void template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_void:"
         << '\n';
    cout << "void:"
         << is_void<void>::value
         << '\n';
    cout << "const void:"
         << is_void<const void>::value
         << '\n';
    cout << "int:"
         << is_void<int>::value
         << '\n';
    cout << "char:"
         << is_void<char>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_void:
void:true
const void:true
int:false
char:false

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_void template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_void:"
         << '\n';
    cout << "double:"
         << is_void<double>::value
         << '\n';
    cout << "float:"
         << is_void<float>::value
         << '\n';
    cout << "volatile void:"
         << is_void<volatile void>::value
         << '\n';
    cout << "const volatile void:"
         << is_void<const volatile void>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_void:
double:false
float:false
volatile void:true
const volatile void:true

```