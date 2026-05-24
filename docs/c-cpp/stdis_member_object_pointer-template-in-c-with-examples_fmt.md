# std::is_member_object_pointer C++ 中的模板，带示例

> 原文: [https://www.geeksforgeeks.org/stdis_member_object_pointer-template-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_member_object_pointer-template-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 `std::is_member_object_pointer` 模板存在于 `<type_traits>` 头文件中。C++ STL 的 `std::is_member_object_pointer` 模板用于检查 `T` 是否是非静态数据成员对象的指针。如果 `T` 是指向非静态数据成员对象类型的指针，则返回布尔值 true，否则返回 false。

## 头文件

```cpp
#include<type_traits>
```

## 模板类

```cpp
template< class T >
struct is_member_object_pointer;
```

## 语法

```cpp
std::is_member_object_pointer<T>::value
```

## 参数

模板 `std::is_member_object_pointer` 接受单个参数 `T` (Trait 类) 检查 `T` 是否是非静态数据成员对象类型的指针。

## 返回值

此模板 `std::is_member_object_pointer` 返回如下所示的布尔变量:

*   **True:** 如果 `T` 是指向非静态数据成员对象类型的指针。
*   **False:** 如果类型 `T` 不是指向非静态数据成员对象类型的指针。

下面是用 C++ 演示 `std::is_member_object_pointer` 的程序:

## 示例程序

```cpp
// C++ program to illustrate
// std::is_member_object_pointer
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare a structure
class GFG {

public:
    int gfg;
};

class A {
};

// Driver Code
int main()
{

// Object to class GFG
    int GFG::*pt = &GFG::gfg;
    cout << boolalpha;

// Check if GFG* is a member object
    // pointer or not
    cout << "GFG*: "
         << is_member_object_pointer<GFG*>::value
         << endl;

// Check if int GFG::* is a member
    // object pointer or not
    cout << "int GFG::*  "
         << is_member_object_pointer<int GFG::*>::value
         << endl;

// Check if int A::* is a member
    // object pointer or not
    cout << "int A::*  "
         << is_member_object_pointer<int A::*>::value
         << endl;

// Check if int A::*() is a member
    // object pointer or not
    cout << "int A::*()  "
         << is_member_object_pointer<int (A::*)()>::value
         << endl;

return 0;
}
```

## 输出

```cpp
GFG*: false
int GFG::*  true
int A::*  true
int A::*()  false
```

## 参考

[http://www.cplusplus.com/reference/type_traits/is_member_object_pointer/](http://www.cplusplus.com/reference/type_traits/is_member_object_pointer/)