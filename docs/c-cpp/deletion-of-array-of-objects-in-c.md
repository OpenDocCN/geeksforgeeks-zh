# c++ 中对象数组的删除

> 原文:[https://www . geeksforgeeks . org/c 中对象数组的删除/](https://www.geeksforgeeks.org/deletion-of-array-of-objects-in-c/)

**<u>需要删除的对象</u> :**

*   为了避免[内存泄漏](https://www.geeksforgeeks.org/what-is-memory-leak-how-can-we-avoid/)，当使用 [**新的**](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/) 动态创建对象时，它会占用[堆部分](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)中的内存。
*   如果没有明确删除对象，那么程序将在运行时崩溃。

**程序 1:** 创建类的对象，该对象是使用 [**新的**](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/) 操作符动态创建的，并使用 [**删除**](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/) 操作符显式删除该对象:

## C++

```cpp
// C++ program to create an object
// dynamically and  delete explicitly
#include <iostream>
using namespace std;

// Class
class Student {

public:
    // Constructor
    Student()
    {
        cout << "Constructor is called!\n";
    }

    // Destructor
    ~Student()
    {
        cout << "Destructor is called!\n";
    }

    // Function to display the message
    void write()
    {
        cout << "Writing!\n";
    }
};

// Driver Code
int main()
{
    // Create an array of objects
    Student* student = new Student();

    // Function Call to write()
    // using instance
    student->write();

    // De-allocate the memory
    // explicitly
    delete student;

    return 0;
}
```

**Output:**

```cpp
Constructor is called!
Writing!
Destructor is called!

```

**程序 2:** 使用**新的**操作符动态创建一个[对象数组](https://www.geeksforgeeks.org/how-to-initialize-array-of-objects-with-parameterized-constructors-in-c/)。每当在运行时创建一个类的对象数组时，程序员就有责任删除它并避免内存泄漏:

## C++

```cpp
// C++ program to create an array of
// objects and deleting it explicitly
#include <iostream>
using namespace std;

// Class
class Student {

public:
    // Constructor
    Student()
    {
        cout << "Constructor is called!\n";
    }

    // Destructor
    ~Student()
    {
        cout << "Destructor is called!\n";
    }

    // Function to display message
    void write()
    {
        cout << "Writing!\n";
    }
};

// Driver Code
int main()
{
    // Create an array of the object
    // dynamically
    Student* student = new Student[3];

    // Function Call to write()
    student[0].write();
    student[1].write();
    student[2].write();

    // De-allocate the memory
    // explicitly
    delete[] student;

    return 0;
}
```

**Output:**

```cpp
Constructor is called!
Constructor is called!
Constructor is called!
Writing!
Writing!
Writing!
Destructor is called!
Destructor is called!
Destructor is called!

```

**程序 3:**

下面是**删除**用于删除对象数组的程序:

## C++

```cpp
// C++ program to delete array of
// objects
#include <iostream>
using namespace std;

// Class
class Student {

public:
    // Constructor
    Student()
    {
        cout << "Constructor is called!\n";
    }

    // Destructor
    ~Student()
    {
        cout << "Destructor is called!\n";
    }

    // Function to display message
    void write()
    {
        cout << "Writing!\n";
    }
};

// Driver Code
int main()
{
    // Create an object dynamically
    Student* student = new Student[3];

    // Function call to write()
    student[0].write();
    student[1].write();
    student[2].write();

    // De-allocate the memory
    // explicitly
    delete student;

    return 0;
}
```

**说明:**这个程序运行时会崩溃。在这个程序中，[构造函数](https://www.geeksforgeeks.org/constructors-c/)工作正常，但是[析构函数](https://www.geeksforgeeks.org/destructors-c/)只对第一个对象执行，之后由于内存泄漏，程序在运行时崩溃。这是因为 3 个对象是在运行时创建的，但只有一个对象被显式删除，这就是为什么剩下的两个对象在运行时崩溃。

**<u>结论</u> :**
在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中，在运行时使用**新的**操作符创建的类的单个对象通过使用****删除**操作符被删除，而对象数组通过使用**删除[]** 操作符被删除，因此不会导致内存泄漏。**