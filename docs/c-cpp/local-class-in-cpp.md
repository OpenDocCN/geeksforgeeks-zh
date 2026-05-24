# c++ 中的局部类

> 原文:[https://www.geeksforgeeks.org/local-class-in-cpp/](https://www.geeksforgeeks.org/local-class-in-cpp/)

在函数内部声明的类成为该函数的局部类，在 C++ 中称为局部类。

*   本地类名只能在本地使用，即只能在函数内部使用，不能在函数外部使用。
*   局部类的方法只能在其中定义。
*   局部类可以有静态函数，但不能有静态数据成员。

例如，在下面的程序中，Test 是 fun()中的一个本地类。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program without any compilation error
// to demonstrate a Local Class
#include <iostream>
using namespace std;

// Creating the class
void fun()
{
    // local to fun
    class Test {
        // members of Test class
    };
}

// Driver Code
int main() { return 0; }
```

### **下面是一些关于 C++ 中局部类的有趣事实:**

**1)** **局部类类型名只能在封闭函数中使用。**

例如，在下面的程序中，t 和 tp 的声明在 fun()中有效，但在 main()中无效。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A program without any compilation error to demonstrate
// that a local class type name can only be used
// in the enclosing function

#include <iostream>
using namespace std;

void fun()
{
    // Local class
    class Test {
        // Body
    };

    Test t; // Fine
    Test* tp; // Fine
}

int main()
{
    Test t; // Error
    Test* tp; // Error
    return 0;
}
```

***(2)*****Local 类的所有方法只能在类内部定义。**例如，程序 1 工作正常，程序 2 编译失败。

**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program without any compilation error to demonstrate
// that all the methods of Local classes must be defined
// inside the class only
#include <iostream>
using namespace std;

void fun()
{
    class Test // local to fun
    {
    public:
        // Fine as the method is defined
        // inside the local class
        void method()
        {
            cout << "Local Class method() called";
        }
    };

    Test t;
    t.method();
}

int main()
{
    fun();
    return 0;
}
```

**Output**

```cpp
Local Class method() called
```

**程序 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program with compilation error to demonstrate that
// all the methods of Local classes must be defined inside
// the class only
#include <iostream>
using namespace std;

void fun()
{
    class Test // local to fun
    {
    public:
        void method();
    };

    // Error as the method is defined outside the local
    // class
    void Test::method() { cout << "Local Class method()"; }
}

int main() { return 0; }
```

**输出**T2】

```cpp
Compiler Error:
 In function 'void fun()':
 error: a function-definition is not allowed here before '{' token
```

**3)局部类不能包含静态数据成员。但是它可能包含静态函数。** 例如，程序 1 编译失败，但程序 2 运行良好。

**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A program with compilation error to demonstrate that
// a Local class cannot contain static data members
#include <iostream>
using namespace std;

void fun()
{
    class Test // local to fun
    {
        static int i;
    };
}

int main() { return 0; }
```

**输出**

```cpp
Compiler Error:
 In function 'void fun()':
 error: local class 'class fun()::Test' shall not have static data member 'int fun()::Test::i'
```

**程序 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program without any compilation error to demonstrate
// that a Local class cannot contain static data members
#include <iostream>
using namespace std;

void fun()
{
    class Test // local to fun
    {
    public:
        static void method()
        {
            cout << "Local Class method() called";
        }
    };

    Test::method();
}

int main()
{
    fun();
    return 0;
}
```

**Output**

```cpp
Local Class method() called
```

**4)** **局部类的成员方法只能访问封闭函数的静态和枚举变量。封闭函数的非静态变量在局部类中不可访问。** 例如，程序 1 编译运行良好。但是，程序 2 在编译中失败了。

**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program without any compilation error to demonstrate
// that member methods of local class can only access static
// and enum variables of the enclosing function
#include <iostream>
using namespace std;

void fun()
{
    static int x;
    enum { i = 1, j = 2 };

    // Local class
    class Test {
    public:
        void method()
        {
            cout << "x = " << x
                 << endl; // fine as x is static
            cout << "i = " << i
                 << endl; // fine as i is enum
        }
    };

    Test t;
    t.method();
}

int main()
{
    fun();
    return 0;
}
```

**Output**

```cpp
x = 0
i = 1
```

**程序 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program with compilation error to demonstrate that
// member methods of local class can only access static
// and enum variables of the enclosing function
#include <iostream>
using namespace std;

void fun()
{
    int x;

    // Local class
    class Test {
    public:
        void method() { cout << "x = " << x << endl; }
    };

    Test t;
    t.method();
}

int main()
{
    fun();
    return 0;
}
```

**错误:**

> prog.cpp:在成员函数‘void fun():Test::method()’中:
> 
> prog.cpp:14:43:错误:使用包含函数自动存储的局部变量
> 
> void method(){ cout < < " x = < < x < < endl；}
> 
> ^
> 
> prog.cpp:9:9:注意:这里声明了' int x '
> 
> int x；
> 
> ^

**5)** **局部类可以访问全局类型、变量**、**和函数。**同样，本地类可以访问相同功能的其他本地类。例如，下面的程序运行良好。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program without any compilation error to demonstrate
// that Local classes can access global types, variables and
// functions
#include <iostream>
using namespace std;

int x;

void fun()
{

    // First Local class
    class Test1 {
    public:
        Test1() { cout << "Test1::Test1()" << endl; }
    };

    // Second Local class
    class Test2 {
        // Fine: A local class can use other local classes
        // of same function
        Test1 t1;

    public:
        void method()
        {
            // Fine: Local class member methods can access
            // global variables.
            cout << "x = " << x << endl;
        }
    };

    Test2 t;
    t.method();
}

int main()
{
    fun();
    return 0;
}
```

**Output**

```cpp
Test1::Test1()
x = 0
```

**必读:**[c++ 中的嵌套类](https://www.geeksforgeeks.org/nested-classes-in-c/)