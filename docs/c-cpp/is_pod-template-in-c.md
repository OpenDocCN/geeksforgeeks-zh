# 是 C++ 中的 _pod 模板

> 原文:[https://www.geeksforgeeks.org/is_pod-template-in-c/](https://www.geeksforgeeks.org/is_pod-template-in-c/)

C++ STL 的 **std::is_pod 模板**用于检查类型是否为纯旧数据(pod)类型。它返回一个显示相同内容的布尔值。

**语法**:

```cpp
template < class T > struct is_pod;

```

**参数**:此模板包含单参数 T (Trait 类)，检查 T 是否为荚型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型是豆荚型。
*   **假**:如果类型是非荚型。

下面的程序说明了 C++ STL 中的标准::is_pod 模板:

**程序 1** :

```cpp
// C++ program to illustrate
// std::is_pod template

#include <iostream>
#include <type_traits>
using namespace std;

struct gfg {
    int var1;
};

struct sam {
    int var2;

private:
    int var3;
};

struct raj {
    virtual void func();
};

int main()
{
    cout << boolalpha;
    cout << "is_pod:" << '\n';
    cout << "gfg:" << is_pod<gfg>::value << '\n';
    cout << "sam:" << is_pod<sam>::value << '\n';
    cout << "raj:" << is_pod<raj>::value << '\n';
    return 0;
}
```

**Output:**

```cpp
is_pod:
gfg:true
sam:false
raj:false

```

**程序 2** :

```cpp
// C++ program to illustrate
// std::is_pod template

#include <iostream>
#include <type_traits>
using namespace std;

class gfg {
    int var1;
};

class sam {
    int var2;

private:
    int var3;
};

class raj {
    virtual void func();
};

int main()
{
    cout << boolalpha;
    cout << "is_pod:" << '\n';
    cout << "gfg:" << is_pod<gfg>::value << '\n';
    cout << "sam:" << is_pod<sam>::value << '\n';
    cout << "raj:" << is_pod<raj>::value << '\n';
    return 0;
}
```

**Output:**

```cpp
is_pod:
gfg:true
sam:true
raj:false

```

**程序 3** :

```cpp
// C++ program to illustrate
// std::is_pod template

#include <iostream>
#include <type_traits>
using namespace std;

union gfg {
    int var1;
};

union sam {
    int var2;

private:
    int var3;
};

int main()
{
    cout << boolalpha;
    cout << "is_pod:" << '\n';
    cout << "gfg:" << is_pod<gfg>::value << '\n';
    cout << "sam:" << is_pod<sam>::value << '\n';
    return 0;
}
```

**Output:**

```cpp
is_pod:
gfg:true
sam:false

```