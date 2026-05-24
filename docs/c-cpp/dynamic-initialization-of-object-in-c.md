# c++ 中对象的动态初始化

> 原文:[https://www . geeksforgeeks . org/c 中对象的动态初始化/](https://www.geeksforgeeks.org/dynamic-initialization-of-object-in-c/)

在本文中，我们将使用[动态构造器](https://www.geeksforgeeks.org/dynamic-constructor-in-c-with-examples/)讨论[对象](https://www.geeksforgeeks.org/c-classes-and-objects/)的动态初始化。

*   对象的动态初始化是指在运行时初始化对象，即在运行时提供对象的初始值。
*   这可以通过使用构造函数并将[参数](https://www.geeksforgeeks.org/constructors-c/)传递给[构造函数](https://www.geeksforgeeks.org/constructors-c/)来实现。
*   当同一个类的多个构造函数具有不同的输入时，这非常方便。

[**动态构造器:**](https://www.geeksforgeeks.org/dynamic-constructor-in-c-with-examples/)

*   运行时用于分配内存的构造函数称为**动态构造函数**。
*   内存在运行时使用[新的](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/)操作符分配，同样，内存在运行时使用[删除](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/)操作符释放。

**<u>动态分配</u> :**

**进场:**

1.  在下面的例子中， **new** 用于动态初始化[默认构造函数](https://www.geeksforgeeks.org/c-internals-default-constructors-set-1/)中的变量，内存分配在[堆](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)上。
2.  geek 类的对象调用该函数，它显示动态分配变量的值，即 ptr。

以下是使用**新的**运算符动态初始化对象的程序:

## C++

```cpp
// C++ program for dynamic allocation
#include <iostream>
using namespace std;

class geeks {
    int* ptr;

public:
    // Default constructor
    geeks()
    {
        // Dynamically initializing ptr
        // using new
        ptr = new int;
        *ptr = 10;
    }

    // Function to display the value
    // of ptr
    void display()
    {
        cout << *ptr << endl;
    }
};

// Driver Code
int main()
{
    geeks obj1;

    // Function Call
    obj1.display();

    return 0;
}
```

**Output**

```cpp
10

```

**<u>动态解除分配</u> :**

**进场:**

1.  在下面的代码中，**删除**用于动态[释放](https://www.geeksforgeeks.org/g-fact-30/)内存。
2.  使用[赋值运算符](https://www.geeksforgeeks.org/assignment-operators-in-c-c/)将对象 obj2 中的 obj1 的内容[覆盖](https://www.geeksforgeeks.org/overloading-new-delete-operator-c/)，然后使用**删除**运算符解除 obj1 的分配。

下面是使用**删除**操作符动态释放内存的代码。

## C++

```cpp
// C++ program to dynamically
// deallocating the memory
#include <iostream>
using namespace std;

class geeks {
    int* ptr;

public:
    // Default constructor
    geeks()
    {
        ptr = new int;
        *ptr = 10;
    }

    // Function to display the value
    void display()
    {
        cout << "Value: " << *ptr
             << endl;
    }
};

// Driver Code
int main()
{
    // Dynamically allocating memory
    // using new operator
    geeks* obj1 = new geeks();
    geeks* obj2 = new geeks();

    // Assigning obj1 to obj2
    obj2 = obj1;

    // Function Call
    obj1->display();
    obj2->display();

    // Dynamically deleting the memory
    // allocated to obj1
    delete obj1;

    return 0;
}
```

**Output**

```cpp
Value: 10
Value: 10

```

下面的 C++ 程序正在演示对象的动态初始化和计算银行存款:

## C++

```cpp
// C++ program to illustrate the dynamic
// initialization as memory is allocated
// to the object
#include <iostream>
using namespace std;

class bank {
    int principal;
    int years;
    float interest;
    float returnvalue;

public:
    // Default constructor
    bank() {}

    // Parameterised constructor to
    // calculate interest(float)
    bank(int p, int y, float i)
    {
        principal = p;
        years = y;
        interest = i/100;
        returnvalue = principal;
        cout << "\nDeposited amount (float):";

        // Finding the interest amount
        for (int i = 0; i < years; i++) {
            returnvalue = returnvalue
                          * (1 + interest);
        }
    }

    // Parameterised constructor to
    // calculate interest(integer)
    bank(int p, int y, int i)
    {
        principal = p;
        years = y;
        interest = float(i)/100;
        returnvalue = principal;
        cout << "\nDeposited amount"
             << " (integer):";

        // Find the interest amount
        for (int i = 0; i < years; i++) {
            returnvalue = returnvalue
                          * (1 + interest);
        }
    }

    // Display function
    void display(void)
    {
        cout << returnvalue
             << endl;
    }
};

// Driver Code
int main()
{
    // Variable initialization
    int p = 200;
    int y = 2;
    int I = 5;
    float i = 2.25;

    // Object is created with
    // float parameters
    bank b1(p, y, i);

    // Function Call with object
    // of class
    b1.display();

    // Object is created with
    // integer parameters
    bank b2(p, y, I);

    // Function Call with object
    // of class
    b2.display();

    return 0;
}
```

**Output**

```cpp
Deposited amount (float):209.101

Deposited amount (integer):220.5

```