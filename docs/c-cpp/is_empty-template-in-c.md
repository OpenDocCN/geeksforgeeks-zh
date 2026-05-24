# 是 C++ 中的 _ 空模板

> 原文:[https://www.geeksforgeeks.org/is_empty-template-in-c/](https://www.geeksforgeeks.org/is_empty-template-in-c/)

C++ STL 的 **std::is_empty 模板**用于检查给定类型是否为空。此方法返回一个布尔值，该值显示给定类型是否为空。

**语法**:

```cpp
template < class T > struct is_empty;

```

**参数**:该模板包含单个参数 **T (Trait 类)**，标识 T 是否为空类型。

**返回值**:该模板返回如下所示的布尔值:

*   **真**:如果类型为空。
*   **假**:如果类型不是空的。

下面的程序说明了 C++ STL 中的 std::is_empty 模板:

**程序 1** :使用结构

```cpp
// C++ program to illustrate
// std::is_empty template

#include <iostream>
#include <type_traits>
using namespace std;

// empty struct
struct GFG1 {
};

// struct with local variable
struct GFG2 {
    int variab;
};

// Struct with global variable
struct GFG3 {
    static int variab;
};

// Struct with virtual destructor
struct GFG4 {
    virtual ~GFG4();
};

// Driver code
int main()
{
    cout << boolalpha;

    cout << "Is GFG1 empty: "
         << is_empty<GFG1>::value
         << '\n';
    cout << "Is GFG2 empty: "
         << is_empty<GFG2>::value
         << '\n';
    cout << "Is GFG3 empty: "
         << is_empty<GFG3>::value
         << '\n';
    cout << "Is GFG4 empty: "
         << is_empty<GFG4>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
Is GFG1 empty: true
Is GFG2 empty: false
Is GFG3 empty: true
Is GFG4 empty: false

```

**程序 2** :使用类

```cpp
// C++ program to illustrate
// std::is_empty template

#include <iostream>
#include <type_traits>
using namespace std;

// empty class
class GFG1 {
};

// class with local variable
class GFG2 {
    int variab;
};

// class with global variable
class GFG3 {
    static int variab;
};

// class with virtual destructor
class GFG4 {
    virtual ~GFG4();
};

int main()
{
    cout << boolalpha;
    cout << "Is GFG1 empty: "
         << is_empty<GFG1>::value
         << '\n';
    cout << "Is GFG2 empty: "
         << is_empty<GFG2>::value
         << '\n';
    cout << "Is GFG3 empty: "
         << is_empty<GFG3>::value
         << '\n';
    cout << "Is GFG4 empty: "
         << is_empty<GFG4>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
Is GFG1 empty: true
Is GFG2 empty: false
Is GFG3 empty: true
Is GFG4 empty: false

```