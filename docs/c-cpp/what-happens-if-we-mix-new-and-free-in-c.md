# 如果我们在 C++ 中混合新的和免费的会发生什么？

> 原文:[https://www . geeksforgeeks . org/如果我们在 c 中混合新的和免费的会发生什么/](https://www.geeksforgeeks.org/what-happens-if-we-mix-new-and-free-in-c/)

我们知道 **[new](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/)** 用于动态创建[内存](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/)，明确删除内存位置是程序员的责任，使用 [**delete**](https://www.geeksforgeeks.org/delete-in-c/) 关键字删除。运行时使用 **new** 关键字创建内存的语法:

> int * ptr = new int；

它将为[类型 int](https://www.geeksforgeeks.org/c-data-types/) 创建一个存储位置，并返回其地址。 **[free()](https://www.geeksforgeeks.org/g-fact-30/)** 只能用于指向使用 **[malloc()](https://www.geeksforgeeks.org/malloc-vs-new/)** 分配的内存的指针或空指针。

**<u>如果我们在 C++ 中混合新的和免费的会发生什么？</u>T3】**

我们知道**新**关键字创建的内存是使用 **delete** 关键字删除的，而 **malloc()** 创建的内存是由 **free()** 删除的。**新建**调用[构造函数](https://www.geeksforgeeks.org/constructors-c/)，**删除**调用[析构函数](https://www.geeksforgeeks.org/destructors-c/)进行内存释放。现在，使用**新建**关键字创建内存，并尝试使用 **free()** 删除它，那么析构函数将不会被调用，因此内存和资源也不会被释放。而且会导致内存和资源泄露。下面是分析 **free()** 和 **delete** 如何表现的程序:

## c++

```cpp
// C++ program to illustrate the working
// of memory allocation if new and free
// are mixed
#include <iostream>
using namespace std;

class A {
private:
    int* p;

public:
    // Default Constructor
    A()
    {
        cout << "Constructor is executed"
             << endl;
        p = new int;
        *p = 5;
    }

    // Destructor
    ~A()
    {
        cout << "Destructor is executed"
             << endl;
        // resource clean-up
        cleanup();
    }

    // Member Function
    void cleanup()
    {
        cout << "Resource clean-"
             << "up completed" << endl;
    }

    // Function to display the value
    // of class variables
    void display()
    {
        cout << "value is: "
             << *p << endl;
    }
};

// Driver Code
int main()
{
    // Create Object of class A
    A* ptr = new A();
    ptr->display();

    // Destructor will be called
    delete ptr;

    A* ptr1 = new A();
    ptr1->display();

    // No destructor will be called
    // hence no resource clean-up
    free(ptr);

    return 0;
}
```

**输出:**

```cpp
Constructor is executed
value is: 5
Destructor is executed
Resource clean-up completed
Constructor is executed
value is: 5

```

**<u>解说</u> :**

在上面的代码中，使用 **new** 关键字创建了一个对象，我们试图使用 **free()** 删除这个对象。它不会调用这个对象的析构函数，这个对象的内存和资源也不会释放。因此，总是建议不要在 [C++ 程序](https://www.geeksforgeeks.org/c-plus-plus/)中混合新的和免费的，以避免额外的努力和时间。