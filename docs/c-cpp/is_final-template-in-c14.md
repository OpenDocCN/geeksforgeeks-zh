# 是 C++ 14 中的 _final 模板

> 原文:[https://www.geeksforgeeks.org/is_final-template-in-c14/](https://www.geeksforgeeks.org/is_final-template-in-c14/)

C++ STL 的 **std::is_final 模板**用于检查类型是否为 final。

**语法**:

```cpp
template < class T > struct is_final;

```

**参数**:本模板包含单参数 **T(性状类)**，检查 T 是否为最终类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是决赛。
*   **False** :如果类型是非最终类型。

下面的程序说明了 C++ STL 中的标准::is_final 模板:

### 注意:请在联机 IDE 中选择 C++ 14 运行代码。

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_final template

#include <iostream>
#include <type_traits>
using namespace std;

// main program

class gfg {
};

class sam final {
}; // using class

int main()
{
    cout << boolalpha;
    cout << "is_final:"
         << '\n';
    cout << "gfg:"
         << is_final<gfg>::value
         << '\n';
    cout << "sam:"
         << is_final<sam>::value
         << '\n';
    cout << "int:"
         << is_final<int>::value
         << '\n';

    return 0;
}
```

**输出:**

```cpp
is_final:
gfg:false
sam:true
int:false

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_final template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
struct gfg {
};

struct sam final {
}; // using struct

int main()
{
    cout << boolalpha;
    cout << "is_final:"
         << '\n';
    cout << "gfg:"
         << is_final<gfg>::value
         << '\n';
    cout << "sam:"
         << is_final<sam>::value
         << '\n';
    cout << "float:"
         << is_final<float>::value
         << '\n';

    return 0;
}
```

**输出:**

```cpp
is_final:
gfg:false
sam:true
float:false

```

**程序 3** :

```cpp
// C++ program to illustrate
// std::is_final template

#include <iostream>
#include <type_traits>
using namespace std;

// main program

// using union
union sam final {
};

union gfg {
};

int main()
{
    cout << boolalpha;
    cout << "is_final:"
         << '\n';
    cout << "sam:"
         << is_final<sam>::value
         << '\n';
    cout << "gfg:"
         << is_final<gfg>::value
         << '\n';
    cout << "char:"
         << is_final<char>::value
         << '\n';

    return 0;
}
```

**输出:**

```cpp
is_final:
sam:true
gfg:false
char:false

```