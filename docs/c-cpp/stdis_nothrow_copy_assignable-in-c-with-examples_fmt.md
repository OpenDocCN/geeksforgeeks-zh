# std::is_nothrow_copy_assignable 在 C++ 中的可赋值性示例

> 原文: [https://www.geeksforgeeks.org/stdis_nothrow_copy_assignable-in-c-with-examples/](https://www.geeksforgeeks.org/stdis_nothrow_copy_assignable-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 `std::is_nothrow_copy_assignable` 模板存在于 `<type_traits>` 头文件中。C++ STL 的 `std::is_nothrow_copy_assignable` 模板是用来检查 `T` 是否是 copy 可赋值类型的，这是众所周知的不抛出任何异常。它返回真或假的布尔值。

## 头文件

```cpp
#include<type_traits>
```

## 模板类

```cpp
template< class T >
struct is_nothrow_copy_assignable;
```

## 语法

```cpp
std::is_nothrow_copy_assignable< datatype >::value << '\n'
```

## 参数

模板 `std::is_nothrow_copy_assignable` 接受单个参数 `T` (Trait 类)检查 `T` 是否为 `is_nothrow_copy_assignable` 类型。

## 返回值

*   `True`: If the given data type `T` is nothrow copy assignable.
*   `false`: If the given data type `T` is not nothrow copy assignable.

下面是用 C++ 演示 `std::is_nothrow_copy_assignable` 的程序:

## 程序

```cpp
// C++ program to illustrate
// std::is_nothrow_copy_assignable
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Declare structures X and Y
struct X {
};

struct Y {
    Y& operator=(const Y&)
    {
        return *this;
    }
};

// Declare classes
class A {
};

class B {
    B() {}
};

class C : B {
};

class D {
    virtual void fn() {}
};

// Driver Code
int main()
{
    cout << std::boolalpha;

    // Check if int is is nothrow
    // copy assignable or not
    cout << "int: "
         << is_nothrow_copy_assignable<int>::value
         << endl;

    // Check if struct X is nothrow
    // copy assignable or not
    cout << "struct X: "
         << is_nothrow_copy_assignable<X>::value
         << endl;

    // Check if struct Y is isnothrow
    // copy assignable or not
    cout << "struct Y: "
         << is_nothrow_copy_assignable<Y>::value
         << endl;

    // Check if int[2] is is nothrow
    // copy assignable or not
    cout << "int[2]: "
         << is_nothrow_copy_assignable<int[2]>::value
         << endl;

    // Check if class A is a nothrow
    // copy assignable or not
    cout << "class A: "
         << is_nothrow_copy_assignable<A>::value
         << endl;

    // Check if class B is a nothrow
    // copy assignable or not
    cout << "class B: "
         << is_nothrow_copy_assignable<B>::value
         << endl;

    // Check if class C is a nothrow
    // copy assignable or not
    cout << "class C: "
         << is_nothrow_copy_assignable<C>::value
         << endl;

    // Check if class D is a nothrow
    // copy assignable or not
    cout << "class D: "
         << is_nothrow_copy_assignable<D>::value
         << endl;
    return 0;
}
```

## 输出

```cpp
int: true
struct X: true
struct Y: false
int[2]: false
class A: true
class B: true
class C: true
class D: true
```

**参考:** [http://www.cplusplus.com/reference/type_traits/is_nothrow_copy_assignable/](http://www.cplusplus.com/reference/type_traits/is_nothrow_copy_assignable/)