# c++ 中新增 vs malloc()和 free()vs delete

> 原文:[https://www . geesforgeks . org/new-vs-malloc-and-free-vs-delete-in-c/](https://www.geeksforgeeks.org/new-vs-malloc-and-free-vs-delete-in-c/)

我们在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中使用 [new 和删除](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/)运算符来动态分配内存，而 [malloc()和 free()](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/) 函数在 C 和 C++ 中也用于相同的目的。 **new 或 malloc()** 和 **delete 或 free()** 的功能似乎相同，但它们在各方面有所不同。
关于构造函数和析构函数调用的行为在以下方面有所不同:
**<u>malloc()vs new():</u>**

*   **malloc():** 它是一个 C 库函数，也可以在 C++ 中使用，而**“new”**运算符只针对 C++ 而言。

*   **malloc()** 和 **new** 都用于在堆中动态分配内存。但是**“新的”**确实调用了类的构造函数，而**“malloc()”**没有。

下面是演示 new 和 malloc()功能的程序:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate malloc()
// and new operator in C++
#include "bits/stdc++.h"
using namespace std;

// Class A
class A {
    int a;

public:
    int* ptr;

    // Constructor of class A
    A()
    {
        cout << "Constructor was Called!"
             << endl;
    }
};

// Driver Code
int main()
{

    // Create an object of class A
    // using new operator
    A* a = new A;
    cout << "Object of class A was "
         << "created using new operator!"
         << endl;

    // Create an object of class A
    // using malloc operator
    A* b = (A*)malloc(sizeof(A));
    cout << "Object of class A was "
         << "created using malloc()!"
         << endl;

    return 0;
}
```

**Output:** 

```cpp
Constructor was Called!
Object of class A was created using new operator!
Object of class A was created using malloc()!
```

在上面的程序中我们可以清楚地看到，在使用**创建对象时，调用了新的运算符** [默认构造函数](https://www.geeksforgeeks.org/c-default-constructor-built-in-types/)，而没有调用 malloc 函数默认构造函数。
**<u>自由()vs 删除:</u>**

*   **free()** 是一个也可以在 C++ 中使用的 C 库函数，而 [**【删除】**](https://www.geeksforgeeks.org/g-fact-30/) 则是一个 C++ 关键字。
*   free()释放内存，但不调用类的[析构函数，而**“删除”**释放内存，也调用类的析构函数。](https://www.geeksforgeeks.org/destructors-c/)

下面是演示 new 和 malloc()功能的程序:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate free()
// and delete keyword in C++
#include "bits/stdc++.h"
using namespace std;

// Class A
class A {
    int a;

public:
    int* ptr;

    // Constructor of class A
    A()
    {
        cout << "Constructor was Called!"
             << endl;
    }

    // Destructor of class A
    ~A()
    {
        cout << "Destructor was Called!"
             << endl;
    }
};

// Driver Code
int main()
{

    // Create an object of class A
    // using new operator
    A* a = new A;
    cout << "Object of class A was "
         << "created using new operator!"
         << endl;

    delete (a);
    cout << "Object of class A was "
         << "deleted using delete keyword!"
         << endl;

    cout << endl;

    A* b = (A*)malloc(sizeof(A));
    cout << "Object of class A was "
         << "created using malloc()!"
         << endl;

    free(b);
    cout << "Object of class A was "
         << "deleted using free()!"
         << endl;

    return 0;
}
```

**Output:** 

```cpp
Constructor was Called!
Object of class A was created using new operator!
Destructor was Called!
Object of class A was deleted using delete keyword!

Object of class A was created using malloc()!
Object of class A was deleted using free()!
```

以下是更多插图的节目:
**节目 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate new, delete
// malloc() and free()
#include "bits/stdc++.h"
using namespace std;

// Class A
class A {
    int a;

public:
    int* ptr;

    // Constructor of class A
    A()
    {
        cout << "Constructor was Called!"
             << endl;
    }

    // Destructor of class A
    ~A()
    {
        cout << "Destructor was Called!"
             << endl;
    }
};

// Driver Code
int main()
{

    // Object Created of class A
    A a;
    return 0;
}
```

**Output:** 

```cpp
Constructor was Called!
Destructor was Called!
```

在上面的程序中，即使没有使用 delete 操作符，析构函数仍然被调用。析构函数调用的原因是语句**“返回 0”**。此语句在主函数中执行时，调用为其创建对象的每个类的析构函数。
为了避免析构函数调用，我们可以将语句“return 0”替换为“exit(0)”。下面是相同的代码:
**程序 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate new, delete
// malloc() and free()
#include "bits/stdc++.h"
using namespace std;

// Class A
class A {
    int a;

public:
    int* ptr;

    // Constructor of class A
    A()
    {
        cout << "Constructor was Called!"
             << endl;
    }

    // Destructor of class A
    ~A()
    {
        cout << "Destructor was Called!"
             << endl;
    }
};

// Driver Code
int main()
{

    // Object Created of class A
    A a;
    exit(0);
}
```

**Output:** 

```cpp
Constructor was Called!
```

**程序 3:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate new, delete
// malloc() and free()
#include "bits/stdc++.h"
using namespace std;

// Class A
class A {
    int a;

public:
    int* ptr;

    // Constructor of class A
    A()
    {
        cout << "Constructor was Called!"
             << endl;
    }

    // Destructor of class A
    ~A()
    {
        cout << "Destructor was Called!"
             << endl;
    }
};

// Driver Code
int main()
{

    // Object Created of class A
    A *a = new A;
    return 0;
}
```

**Output:** 

```cpp
Constructor was Called!
```

即使在使用语句**“返回 0”**之后，也没有析构函数调用。原因在于分配一个类的对象的不同。当我们在一个块内创建一个带有**类名 object_name** 的对象时，该对象有一个自动存储持续时间，即它将在超出范围时自动销毁。但是当我们使用**新类名**时，对象有一个动态存储持续时间，这意味着必须使用 **delete** 关键字显式删除它。