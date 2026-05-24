# 是 C++ 中的 _ const Template

> 原文:[https://www.geeksforgeeks.org/is_const-template-in-c/](https://www.geeksforgeeks.org/is_const-template-in-c/)

C++ STL 的 **std::is_const 模板**用于检查类型是否为常量限定类型。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template  < class T >struct is_const;

```

**模板参数**:该模板包含单参数 **T(性状类)**，检查 T 是否为常量限定类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是常量限定的。
*   **False** :如果类型是非常量限定的。

下面的程序说明了 C++ STL 中的 is_const 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// is_const

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_const:"
         << endl;
    cout << "int:"
         << is_const<int>::value
         << '\n';
    cout << "const int:"
         << is_const<const int>::value
         << '\n';
    cout << "const int&:"
         << is_const<typename remove_reference<const int&>::type>::value
         << '\n';
    return 0;
}
```

**Output:**

```cpp
is_const:
int:false
const int:true
const int&:true

```

**程序 2** :

```cpp
// C++ program to illustrate
// is_const

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_const:"
         << endl;
    cout << "const int*:"
         << is_const<const int*>::value
         << '\n';
    cout << "int* const:"
         << is_const<int* const>::value
         << '\n';
    cout << "const int&:"
         << is_const<const int&>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_const:
const int*:false
int* const:true
const int&:false

```

**程序 3** :

```cpp
// C++ program to illustrate
// is_const

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_const:"
         << endl;
    cout << "float:"
         << is_const<float>::value
         << '\n';
    cout << "const float:"
         << is_const<const float>::value
         << '\n';
    cout << "char const:"
         << is_const<char const>::value
         << '\n';
    cout << "double:"
         << is_const<double>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_const:
float:false
const float:true
char const:true
double:false

```