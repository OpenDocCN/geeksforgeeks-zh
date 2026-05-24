# c++ 中静态函数和常量函数的区别

> 原文:[https://www . geesforgeks . org/static-and-constant-function in-CPP/](https://www.geeksforgeeks.org/difference-between-static-and-constant-function-in-cpp/)

[**静态功能**](https://www.geeksforgeeks.org/what-are-static-functions-in-c/) **:** 是成员功能，仅用于访问[静态数据成员](https://www.geeksforgeeks.org/static-data-members-c/)。它不能访问非静态数据成员，甚至不能调用非静态成员函数。即使不存在该类的对象，也可以调用它。它还用于在类的不同对象之间维护类成员函数的单一副本。

**程序 1:**

## C++

```cpp
// C++ program to illustrate the use
// of static function
#include "bits/stdc++.h"
using namespace std;

class A {
public:
    static void f()
    {
        cout << "GeeksforGeeks!";
    }
};

// Driver Code
int main()
{
    A::f();
}
```

**Output:**

```cpp
GeeksforGeeks!

```

[**常量函数**](https://www.geeksforgeeks.org/const-member-functions-c/) **:** 是程序中一般声明为常量的函数。它还保证不允许修改对象或调用任何非常量成员函数。它指定函数是只读函数，并且不修改为其调用的对象。

**程序 2:**

## C++

```cpp
// C++ program to illustrate the use
// of const keyword

#include <iostream>
using namespace std;

// Driver Code
int main()
{
    const double a = 1;

    // Using the below line of code
    // gives error
    // a = 2.21;

    cout << a << endl;

    return 0;
}
```

**Output:**

```cpp
1

```

**表格静态函数与常量函数的区别:**

<figure class="table">它是用[静态关键字](https://www.geeksforgeeks.org/static-keyword-cpp/)来声明的。

| 

**静态函数**

 | 

**常量函数**

 |
| --- | --- |
| Use [const keyword](https://www.geeksforgeeks.org/const-keyword-in-cpp/) to declare. |
| You are not allowed to modify variables or data members or functions again. Instead, it is assigned to the entire life cycle of the program. | Specifies whether the variable can be modified. |
| It is helpful to call functions that use classes without using objects. | We help avoid modifying objects. |
| This function can only be called by static data members and static member functions. | This function can be called using any type of object. |
| It is useful to declare the global data that should be updated when the program resides in memory, to restrict access to functions, and to reuse the same function names in other files. | It is used with the pointer or reference passed to the function to avoid unexpected changes to the object, and can be called by any type of object, etc. |
| It is a member function, and it is generally allowed to use classes to access functions instead of using instances of classes. | Is a member function that is generally declared as a constant in a program. |

</figure>