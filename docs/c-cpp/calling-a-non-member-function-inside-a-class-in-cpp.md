# 在 C++ 中调用类内部的非成员函数

> 原文:[https://www . geesforgeks . org/calling-a-非成员-函数-在 cpp 中的类内/](https://www.geeksforgeeks.org/calling-a-non-member-function-inside-a-class-in-cpp/)

**成员函数:**是一个[函数](https://www.geeksforgeeks.org/functions-in-c/)可以声明为一个[类](https://www.geeksforgeeks.org/c-classes-and-objects/)的成员。它通常在类定义中声明，并对同一类的数据成员起作用。它可以访问同一类的[私有、公共和受保护的](https://www.geeksforgeeks.org/access-modifiers-in-c/)数据成员。该函数声明如下:

## c++

```cpp
// Given Class
class memberdemo {
private:
    {
    public:
        {
            void check();
        }

        // Member Function
        trial::void check();
    }
}
```

**非成员函数:**在类外声明的函数称为该类的非成员函数。下面是两者的区别:

*   Member functions can appear outside the class body (for example, in the implementation file). However, according to this method, the member function must be qualified by its class name. This is to identify that the function is a member of a specific class. But non-member functions always appear outside the class.
*   Another difference between member functions and non-member functions is how they are called in the main routine.

**<u>节目 1</u> :**

## C++

```cpp
// C++ to illustrate the above concepts
#include <iostream>
using namespace std;

class A {
    int a;

public:
    // Member function
    void memberfn(int x)
    {
        a = x;
        cout << "Member function inside"
             << " class declared\n";
    }

    // Member function but definition
    // outside the class
    void memberfn2();
};

// Member function declared with
// scope resolution operator
void A::memberfn2()
{
    cout << "Member function but declared "
         << " outside the class\n";
}

// Non-member function
void nonmemberfn()
{
    cout << "Non-member function\n";
}

// Driver Code
int main()
{
    // Object of class A
    A obj;

    // Calling Member Function
    obj.memberfn(5);
    obj.memberfn2();

    // Calling Non-Member Function
    nonmemberfn();

    return 0;
}
```

**Output:**

```cpp
Member function inside class declared
Member function but declared  outside the class
Non-member function

```

**解释:**从上面的程序来看，有三种情况:

*   Declare and define a member function in the class and call it using the object of the class.
*   Members are declared in the class, but defined outside the class, and called using the object of the class.
*   Non-member functions declared outside the class but calling ordinary functions inside the main function.

现在，这里的问题出现了**在程序中是否有可能调用成员函数内部的非成员函数。答案是肯定的**。下面是说明如何在成员函数中调用非成员函数的程序:

**<u>程序二</u>:**

## c++

```cpp
// C++ program to illustrate the
// above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the factorial
// of the number N
int fact(int n)
{
    if (n == 0 || n == 1)
        return 1;
    else
        return n * fact(n - 1);
}

// Class Examples
class example {
    int x;

public:
    void set(int x) { this->x = x; }

    // Calling the non-member function
    // inside the function of class
    int find() { return fact(x); }
};

// Driver Code
int main()
{
    // Object of the class
    example obj;

    obj.set(5);

    // Calling the member function
    cout << obj.find();

    return 0;
}
```

**输出:**

```cpp
120

```

**说明:**成员函数内部可以调用非成员函数，但条件是必须在成员函数之前声明非成员函数。在上面的例子中，遵循了相同的方法，并且可以调用非成员函数，因此答案是 **5** 的[因子](https://www.geeksforgeeks.org/program-for-factorial-of-a-number/)，即 **120** 。