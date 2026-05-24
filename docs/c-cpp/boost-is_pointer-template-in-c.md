# c++ 中 boost is_pointer 模板

> 原文:[https://www . geesforgeks . org/boost-is _ pointer-template-in-c/](https://www.geeksforgeeks.org/boost-is_pointer-template-in-c/)

Boost 库的 **is_pointer** 模板用于检查给定类型是否为指针。它返回一个显示相同内容的布尔值。

**头文件:**

```cpp
#include "boost/type_traits.hpp"
 or 
#include "boost/type_traits/is_pointer.hpp"

```

**模板类:**

```cpp
template <class T>
struct is_pointer : public true_type-or-false_type {};

```

如果 T 是指针类型，则从 true 类型继承，否则从 false 类型继承。

**语法:**

```cpp
boost::is_pointer::value
boost::is_pointer::value_type

```

**参数:**该模板接受单个参数 **T(Trait 类)**检查 T 是否为指针类型。

**接受的参数:**该模板接受以下参数:

```cpp
typename T
T *volatile
T *const volatile
T *const
T *

```

**返回值:**该模板返回如下所示的布尔值:

*   **真:**如果类型是指针值。
*   **False:** 如果类型不是指针值。

下面的程序说明了 C++ STL 中的 **std::is_pointer 模板**:

**程序 1:**

```cpp
// C++ program to illustrate
// std::is_floating_point template
#include <bits/stdc++.h>
#include <boost/type_traits/is_pointer.hpp>
#include <boost/typeof/typeof.hpp>
using namespace std;

// Main Program
int main()
{
    cout << "is_pointer_type: \n";
    cout << "int *: "
         << boost::is_pointer<int*>::value << "\n";
    cout << "char *: "
         << boost::is_pointer<char*>::value
         << "\n";

    // Pointer to integer
    int* a;
    cout << "pointer to integer: "
         << boost::is_pointer<decltype(a)>::value
         << "\n";

    // Pointer to 1D array
    int* b = new int[29];
    cout << "pointer to 1-D array: "
         << boost::is_pointer<decltype(b)>::value
         << "\n";

    // 1-D array
    int c[20];
    cout << "1-D array :"
         << boost::is_pointer<decltype(c)>::value
         << "\n";

    return 0;
}
```

**Output:**

```cpp
is_pointer_type: 
int *: 1
char *: 1
pointer to integer: 1
pointer to 1-D array: 1
1-D array :0

```

**程序 2:**

```cpp
// C++ program to illustrate
// std::is_floating_point template
#include <bits/stdc++.h>
#include <boost/type_traits/is_pointer.hpp>
#include <boost/typeof/typeof.hpp>
using namespace std;

// Function with an integer
// argument and void return type
void fun(int x)
{
    cout << "value of x is : " << x << "\n";
}

// A Structure
struct A {
    int x;
    char a[8];
};

// A Class
class student {
    int roll;
    string name;

public:
    // Student Class Constructor
    student(int x, string y)
    {
        roll = x;
        name = y;
    }

    // Member function to get the
    // name of a student
    string get_name()
    {
        return name;
    }

    // Member function to get the
    // roll number of a student
    int get_roll()
    {
        return roll;
    }
};

// Main Program
int main()
{
    cout << "is_pointer_type: \n";

    // Pointer to function
    void (*ptr)(int) = &fun;
    cout << "pointer to fun: "
         << boost::is_pointer<decltype(ptr)>::value
         << "\n";

    // Instance of A
    A obj;
    cout << "instance of a structure: "
         << boost::is_pointer<decltype(obj)>::value
         << "\n";

    // Pointer to instance of A
    A* obj2;
    cout << "pointer to instance of a structure: "
         << boost::is_pointer<decltype(obj2)>::value
         << "\n";

    // Instance of student
    student s(11840220, "GeeksforGeeks");
    cout << "instance of a class: "
         << boost::is_pointer<decltype(s)>::value
         << "\n";

    // Pointer to instance of student
    student* S;
    S = &s;
    cout << "pointer to instance of a class: "
         << boost::is_pointer<decltype(S)>::value
         << "\n";

    return 0;
}
```

**Output:**

```cpp
is_pointer_type: 
pointer to fun: 1
instance of a structure: 0
pointer to instance of a structure: 1
instance of a class: 0
pointer to instance of a class: 1

```