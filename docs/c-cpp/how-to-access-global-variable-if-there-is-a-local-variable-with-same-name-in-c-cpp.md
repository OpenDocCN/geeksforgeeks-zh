# C/c++ 中有同名局部变量如何访问全局变量？

> 原文:[https://www . geesforgeks . org/如何访问-全局变量-如果有-局部变量-同名-in-c-cpp/](https://www.geeksforgeeks.org/how-to-access-global-variable-if-there-is-a-local-variable-with-same-name-in-c-cpp/)

**局部变量:**其作用域位于声明它们的函数或块内部的变量。

**全局变量:**存在于所有函数之外的变量。它是从所有其他范围可见的变量。

如果 C 和 C++ 中有同名的局部变量，我们可以分别通过 **Extern** 和**作用域解析运算符**来访问全局变量。

### **In C:**

**1)** 如果我们在 C 中有一个同名的局部变量，我们可以使用**[**extern**](https://www.geeksforgeeks.org/understanding-extern-keyword-in-c/)**来访问一个全局变量。****

## **C**

```cpp
// C Program to demonstrate that we can access a global
// variable if we have a local variable with same name
#include <stdio.h>

// Global variable x
int x = 50;

int main()
{
    // Local variable x
    int x = 10;
    {
        extern int x;
        printf("Value of global x is %d\n", x);
    }
    printf("Value of local x is %d\n", x);
    return 0;
}
```

****Output**

```cpp
Value of global x is 50
Value of local x is 10
```** 

### ****在 C++ 中:****

****2)** 如果我们在 C++ 中有一个同名的局部变量，我们可以使用 [**作用域解析运算符(:::)来访问一个全局变量。**](https://www.geeksforgeeks.org/scope-resolution-operator-in-c/)**

## **c++**

```cpp
// C++ Program to demonstrate that We can access a global
// variable if we have a local variable with same name in
// C++ using Scope resolution operator (::)
#include <iostream>
using namespace std;

// Global variable x
int x = 50;

int main()
{
    // Local variable x
    int x = 10;
    cout << "Value of global x is " << ::x << endl;
    cout << "Value of local x is " << x;
    getchar();
    return 0;
}
```

****输出**

```cpp
Value of global x is 50
Value of local x is 10
```** 

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**