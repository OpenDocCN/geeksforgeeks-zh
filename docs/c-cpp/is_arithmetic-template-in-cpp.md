# 是 C++ 中的 _ 算术模板

> 原文:[https://www . geesforgeks . org/is _ algorithm-template-in-CPP/](https://www.geeksforgeeks.org/is_arithmetic-template-in-cpp/)

C++ STL 的**STD::is _ 算术模板**用于检查给定类型是否为算术。算术类型是指整型或浮点型。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template <class T> struct is_arithmetic;
```

**参数**:本模板接受单个参数 **T(性状类)**，检查 T 是否为算术类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是算术。
*   **假**:如果类型是非算术。

下面的程序说明了 C++ STL 中的标准::is _ 算术模板:

**程序 1** :

```cpp
// C++ program to illustrate
// is_arithmetic template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
class GFG {
};

int main()
{
    cout << boolalpha;
    cout << "is_arithmetic:" << '\n';
    cout << "GFG: "
         << is_arithmetic<GFG>::value << '\n';
    cout << "bool: "
         << is_arithmetic<bool>::value << '\n';
    cout << "long: "
         << is_arithmetic<long>::value << '\n';
    cout << "short: "
         << is_arithmetic<short>::value << '\n';
    return 0;
}
```

**Output:**

```cpp
is_arithmetic:
GFG: false
bool: true
long: true
short: true

```

**程序 2** :

```cpp
// C++ program to illustrate
// is_arithmetic template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
class GFG {
};

int main()
{
    cout << boolalpha;
    cout << "is_arithmetic:" << '\n';
    cout << "GFG: "
         << is_arithmetic<GFG>::value << '\n';
    cout << "int: "
         << is_arithmetic<int>::value << '\n';
    cout << "int const: "
         << is_arithmetic<int const>::value << '\n';
    cout << "int &: "
         << is_arithmetic<int&>::value << '\n';
    cout << "int *: "
         << is_arithmetic<int*>::value << '\n';
    cout << "long int: "
         << is_arithmetic<long int>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
is_arithmetic:
GFG: false
int: true
int const: true
int &: false
int *: false
long int: true

```

**程序 3** :

```cpp
// C++ program to illustrate
// is_arithmetic template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_arithmetic:" << '\n';
    cout << "float: "
         << is_arithmetic<float>::value << '\n';
    cout << "float const: "
         << is_arithmetic<float const>::value << '\n';
    cout << "float &: "
         << is_arithmetic<float&>::value << '\n';
    cout << "float *: "
         << is_arithmetic<float*>::value << '\n';
    cout << "double: "
         << is_arithmetic<double>::value << '\n';
    cout << "double const: "
         << is_arithmetic<double const>::value << '\n';
    cout << "double &: "
         << is_arithmetic<double&>::value << '\n';
    cout << "double *: "
         << is_arithmetic<double*>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
is_arithmetic:
float: true
float const: true
float &: false
float *: false
double: true
double const: true
double &: false
double *: false

```

**程序 4** :

```cpp
// C++ program to illustrate
// is_arithmetic template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_arithmetic:" << '\n';
    cout << "char: "
         << is_arithmetic<char>::value << '\n';
    cout << "char const: "
         << is_arithmetic<char const>::value << '\n';
    cout << "char &: "
         << is_arithmetic<char&>::value << '\n';
    cout << "char *: "
         << is_arithmetic<char*>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
is_arithmetic:
char: true
char const: true
char &: false
char *: false

```