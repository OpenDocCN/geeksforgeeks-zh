# 是 C++ 中的 _signed 模板

> 原文:[https://www.geeksforgeeks.org/is_signed-template-in-c/](https://www.geeksforgeeks.org/is_signed-template-in-c/)

C++ STL 的 **std::is_signed 模板**用于检查类型是否为有符号算术类型。

**语法**:

```cpp
template <class T > struct is_signed;

```

**参数**:此模板包含单参数 **T (Trait 类)**检查 T 是否为有符号算术类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是有符号算术类型。
*   **False** :如果类型为无符号算术类型。

下面的程序说明了 C++ STL 中的标准::is_signed 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_signed template

#include <iostream>
#include <type_traits>
using namespace std;

class gfg {
};

enum sam : int {};
enum class raj : int {};

int main()
{
    cout << boolalpha;
    cout << "is_signed:" << '\n';
    cout << "int:" << is_signed<int>::value << '\n';
    cout << "gfg:" << is_signed<gfg>::value << '\n';
    cout << "sam:" << is_signed<sam>::value << '\n';
    cout << "raj:" << is_signed<raj>::value << '\n';
    return 0;
}
```

**Output:**

```cpp
is_signed:
int:true
gfg:false
sam:false
raj:false

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_signed template

#include <iostream>
#include <type_traits>
using namespace std;

int main()
{
    cout << boolalpha;
    cout << "is_signed:" << '\n';
    cout << "float:"
         << is_signed<float>::value << '\n';
    cout << "signed int:"
         << is_signed<signed int>::value << '\n';
    cout << "unsigned int:"
         << is_signed<unsigned int>::value << '\n';
    return 0;
}
```

**Output:**

```cpp
is_signed:
float:true
signed int:true
unsigned int:false

```

**程序 3** :

```cpp
// C++ program to illustrate
// std::is_signed template

#include <iostream>
#include <type_traits>
using namespace std;

int main()
{
    cout << boolalpha;
    cout << "is_signed:" << '\n';
    cout << "bool:" << is_signed<bool>::value << '\n';
    cout << "unsigned char:"
         << is_signed<unsigned char>::value << '\n';
    cout << "signed char:"
         << is_signed<signed char>::value << '\n';
    cout << "double:"
         << is_signed<double>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
is_signed:
bool:false
unsigned char:false
signed char:true
double:true

```