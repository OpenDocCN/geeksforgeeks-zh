# 是 C++ 中的 _ 无符号模板

> 原文:[https://www.geeksforgeeks.org/is_unsigned-template-in-c/](https://www.geeksforgeeks.org/is_unsigned-template-in-c/)

C++ STL 的 **std::is_unsigned 模板**用于检查类型是否为无符号算术类型。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template <class T > struct is_unsigned;

```

**参数**:此模板包含单参数 **T (Trait 类)**检查 T 是否为无符号算术类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是无符号算术类型。
*   **False** :如果类型是有符号算术类型。

下面的程序说明了 C++ STL 中的标准::is_unsigned 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_unsigned template

#include <iostream>
#include <type_traits>
using namespace std;

class gfg {
};

enum sam : unsigned {};
enum class raj : unsigned {};

int main()
{
    cout << boolalpha;
    cout << "is_unsigned:" << '\n';
    cout << "unsigned int:"
         << is_unsigned<unsigned int>::value << '\n';
    cout << "gfg:"
         << is_unsigned<gfg>::value << '\n';
    cout << "sam:"
         << is_unsigned<sam>::value << '\n';
    cout << "raj:"
         << is_unsigned<raj>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
is_unsigned:
unsigned int:true
gfg:false
sam:false
raj:false

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_unsigned template

#include <iostream>
#include <type_traits>
using namespace std;

int main()
{
    cout << boolalpha;
    cout << "is_unsigned:" << '\n';
    cout << "signed char:"
         << is_unsigned<signed char>::value << '\n';
    cout << "unsigned char:"
         << is_unsigned<unsigned char>::value << '\n';
    cout << "signed int:"
         << is_unsigned<signed int>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
is_unsigned:
signed char:false
unsigned char:true
signed int:false

```

**程序 3** :

```cpp
// C++ program to illustrate
// std::is_unsigned template

#include <iostream>
#include <type_traits>
using namespace std;

int main()
{
    cout << boolalpha;
    cout << "is_unsigned:" << '\n';
    cout << "bool:"
         << is_unsigned<bool>::value << '\n';
    cout << "float:"
         << is_unsigned<float>::value << '\n';
    cout << "double:"
         << is_unsigned<double>::value << '\n';

    return 0;
}
```

**Output:**

```cpp
is_unsigned:
bool:true
float:false
double:false

```