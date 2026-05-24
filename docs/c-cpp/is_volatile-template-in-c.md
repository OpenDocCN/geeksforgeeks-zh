# 是 C++ 中的 _volatile 模板

> 原文:[https://www.geeksforgeeks.org/is_volatile-template-in-c/](https://www.geeksforgeeks.org/is_volatile-template-in-c/)

C++ STL 的 **std::is_volatile 模板**用于检查类型是否是 volatile 限定的。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template < class T > struct is_volatile;

```

**参数**:该模板包含单参数 **T (Trait 类)**，检查 T 是否为易失性合格类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是易失性合格的。
*   **假**:如果类型是非易失性合格的。

下面的程序说明了 C++ STL 中的标准::is_volatile 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_volatile template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_volatile:"
         << '\n';
    cout << "volatile int:"
         << is_volatile<volatile int>::value
         << '\n';
    cout << "volatile void:"
         << is_volatile<volatile void>::value
         << '\n';
    cout << "int:"
         << is_volatile<int>::value
         << '\n';
    cout << "char:"
         << is_volatile<char>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_volatile:
volatile int:true
volatile void:true
int:false
char:false

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_volatile template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_volatile:"
         << '\n';
    cout << "double:"
         << is_volatile<double>::value
         << '\n';
    cout << "float:"
         << is_volatile<float>::value
         << '\n';
    cout << "const volatile void:"
         << is_volatile<const volatile void>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_volatile:
double:false
float:false
const volatile void:true

```

**程序 3** :

```cpp
// C++ program to illustrate
// std::is_volatile template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_volatile:"
         << '\n';
    cout << "volatile double:"
         << is_volatile<volatile double>::value
         << '\n';
    cout << "volatile float:"
         << is_volatile<volatile float>::value
         << '\n';
    cout << "bool:"
         << is_volatile<bool>::value
         << '\n';
    cout << "volatile char:"
         << is_volatile<volatile char>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_volatile:
volatile double:true
volatile float:true
bool:false
volatile char:true

```