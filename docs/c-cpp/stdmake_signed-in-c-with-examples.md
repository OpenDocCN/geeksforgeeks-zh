# 标准::make _ signed c++ 示例

> 原文:[https://www . geesforgeks . org/stdmake _ sign-in-c-with-examples/](https://www.geeksforgeeks.org/stdmake_signed-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::make_signed** 模板存在于**T16】type _ traits>T5】头文件中。C++ STL 的 **std::make_signed** 模板用于通过保留任何 cv 限定符来获取 **T(铁人三项类)**对应的有符号类型。可以使用**STD::is _ same**功能检查给定类型 **T** 是否为有符号类型。**

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template< class T >
struct make_signed;

template<class T>
using make_signed_t 
    = typename make_signed<T>::type;

```

**语法:**

```cpp
std::make_signed<T>::type

```

**参数:**模板 **std::make_signed** 接受单个参数 **T(Trait 类)**并将类型 T 作为有符号类型。

以下是在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中演示 **std::make_signed** 的程序:

**程序:**

```cpp
// C++ program to illustrate
// std::make_signed
// make_signed
#include <iostream>
#include <type_traits>
using namespace std;

// Declare enum
enum ENUM1 { a,
             b,
             c };

enum class ENUM2 : unsigned char { x,
                                   y,
                                   z };

// Driver Code
int main()
{

    // Declare variable using make_signed
    // for int, unsigned, const unsigned,
    // enum1 and enum2
    typedef make_signed<int>::type A;
    typedef make_signed<unsigned>::type B;
    typedef make_signed<const unsigned>::type C;
    typedef make_signed<ENUM1>::type D;
    typedef make_signed<ENUM2>::type E;

    cout << boolalpha;

    // Check if the above declared variables
    // are signed type or not
    cout << "A is signed type? "
         << is_same<int, A>::value
         << endl;

    cout << "B is signed type? "
         << is_same<int, B>::value
         << endl;

    cout << "C is signed type? "
         << is_same<int, C>::value
         << endl;

    cout << "D is signed type? "
         << is_same<int, D>::value
         << endl;

    cout << "E is signed type? "
         << is_same<int, E>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
A is signed type? true
B is signed type? true
C is signed type? false
D is signed type? true
E is signed type? false

```

**参考:**T2】http://www.cplusplus.com/reference/type_traits/make_signed/