# 是 C++ 中的 _ 指针模板

> 原文:[https://www.geeksforgeeks.org/is_pointer-template-in-cpp/](https://www.geeksforgeeks.org/is_pointer-template-in-cpp/)

C++ STL 的 **std::is_pointer 模板**用于检查给定类型是否为指针。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template <class T > struct is_pointer;
```

**参数**:本模板接受单个参数 **T (Trait 类)**检查 T 是否为指针。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是指针。
*   **False** :如果类型是非指针。

下面的程序说明了 C++ STL 中的标准::is_pointer 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// is_pointer template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
class GFG {
};

int main()
{
    cout << boolalpha;
    cout << "is_pointer:"
         << endl;
    cout << "GFG: "
         << is_pointer<GFG>::value << '\n';
    cout << "GFG*: "
         << is_pointer<GFG*>::value << '\n';
    cout << "GFG&: "
         << is_pointer<GFG&>::value << '\n';
    cout << "nullptr_t: "
         << is_pointer<nullptr_t>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
is_pointer:
GFG: false
GFG*: true
GFG&: false
nullptr_t: false

```

**程序 2** :

```cpp
// C++ program to illustrate
// is_pointer template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_pointer:"
         << endl;
    cout << "int: "
         << is_pointer<int>::value << '\n';
    cout << "int *: "
         << is_pointer<int*>::value << '\n';
    cout << "int **: "
         << is_pointer<int**>::value << '\n';
    cout << "int ***: "
         << is_pointer<int***>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
is_pointer:
int: false
int *: true
int **: true
int ***: true

```

**程序 3** :

```cpp
// C++ program to illustrate
// is_pointer template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{

    cout << boolalpha;
    cout << "is_pointer:" << endl;
    cout << "int *&: "
         << is_pointer<int*&>::value << '\n';
    cout << "int *[10]: "
         << is_pointer<int * [10]>::value << '\n';
    cout << "float *: "
         << is_pointer<float*>::value << '\n';
    cout << "int[10]:"
         << is_pointer<int[10]>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
is_pointer:
int *&: false
int *[10]: false
float *: true
int[10]:false

```