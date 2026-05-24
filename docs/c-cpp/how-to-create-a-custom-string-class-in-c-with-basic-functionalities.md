# 如何使用基本功能在 C++ 中创建自定义字符串类

> 原文:[https://www . geesforgeks . org/如何使用基本功能创建自定义字符串类/](https://www.geeksforgeeks.org/how-to-create-a-custom-string-class-in-c-with-basic-functionalities/)

在本文中，我们将创建我们的自定义字符串类，它将具有与现有的[字符串类](https://www.geeksforgeeks.org/c-string-class-and-its-applications/)相同的功能。
字符串类具有以下基本功能:

1.  **不带参数的构造函数:**这将为堆中的字符串对象分配存储空间，并将该值指定为[空字符](https://www.geeksforgeeks.org/difference-between-null-pointer-null-character-0-and-0-in-c-with-examples/)。
2.  **只有一个参数的构造函数:**它接受一个指向一个字符的指针，或者我们可以说，如果我们传递一个字符数组，接受指向数组中第一个字符的指针，那么 String 类的构造函数会在[堆内存](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)上分配与传递的数组大小相同的存储空间，并将数组的内容复制到堆中[分配的内存](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/)上。它使用在 cstring 库中声明的 [strcpy()](https://www.geeksforgeeks.org/strcpy-in-c-cpp/) 函数复制内容。
    在执行上述操作之前，它会检查传递的参数是否是[空指针](https://www.geeksforgeeks.org/few-bytes-on-null-pointer-in-c/)，然后它会表现为没有参数的构造函数。
3.  **复制构造器:**当从已经创建的对象创建的相同类型的任何对象时调用它，然后它执行**深度复制**。它在堆上为要创建的对象分配新的空间，并复制传递的对象的内容(作为引用传递)。
4.  **移动构造函数:**通常在从同一类型的右值初始化对象(通过直接初始化或复制初始化)时调用。它接受对自定义字符串类类型的对象的[值的引用。](https://www.geeksforgeeks.org/lvalue-and-rvalue-in-c-language/)

下面是使用自定义字符串类 **Mystring** :
实现上述方法

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// above discussed functionality
#include <cstring>
#include <iostream>
using namespace std;

// Custom string class
class Mystring {

    // Initialise the char array
    char* str;

public:
    // No arguments Constructor
    Mystring();

    // Constructor with 1 arguments
    Mystring(char* val);

    // Copy Constructor
    Mystring(const Mystring& source);

    // Move Constructor
    Mystring(Mystring&& source);

    // Destructor
    ~Mystring() { delete str; }
};

// Function to illustrate Constructor
// with no arguments
Mystring::Mystring()
    : str{ nullptr }
{
    str = new char[1];
    str[0] = '\0';
}

// Function to illustrate Constructor
// with one arguments
Mystring::Mystring(char* val)
{
    if (val == nullptr) {
        str = new char[1];
        str[0] = '\0';
    }

    else {

        str = new char[strlen(val) + 1];

        // Copy character of val[]
        // using strcpy
        strcpy(str, val);
        str[strlen(val)] = '\0';

        cout << "The string passed is: "
             << str << endl;
    }
}

// Function to illustrate
// Copy Constructor
Mystring::Mystring(const Mystring& source)
{
    str = new char[strlen(source.str) + 1];
    strcpy(str, source.str);
    str[strlen(source.str)] = '\0';
}

// Function to illustrate
// Move Constructor
Mystring::Mystring(Mystring&& source)
{
    str = source.str;
    source.str = nullptr;
}

// Driver Code
int main()
{
    // Constructor with no arguments
    Mystring a;

    // Convert string literal to
    // char array
    char temp[] = "Hello";

    // Constructor with one argument
    Mystring b{ temp };

    // Copy constructor
    Mystring c{ a };

    char temp1[] = "World";

    // One arg constructor called,
    // then the move constructor
    Mystring d{ Mystring{ temp } };
    return 0;
}
```

**Output:** 

```cpp
The string passed is: Hello
The string passed is: Hello
```