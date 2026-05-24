# c++ 中不同引用的重载

> 原文:[https://www . geesforgeks . org/overloads-of-the-different-references-in-c/](https://www.geeksforgeeks.org/overloads-of-the-different-references-in-c/)

本文主要关注通过引用的函数/方法重载，以及可以传递的参数类型。

**先决条件:**

*   [l 值参考](https://www.geeksforgeeks.org/lvalues-references-and-rvalues-references-in-c-with-examples/)。
*   r 值引用。
*   [移动语义–STD::Move()](https://www.geeksforgeeks.org/stdmove-in-utility-in-c-move-semantics-move-constructors-and-move-assignment-operators/)。

**概述:**
l 值指的是识别一个对象的内存位置。r-value 指的是存储在内存中某个地址的数据值。[c++ 中的引用](https://www.geeksforgeeks.org/references-in-c/)只不过是已经存在的变量的替代。它们是使用变量名称前的“&”声明的。右值引用是现代 C++ 兴起以来(即 [C++ 11](https://www.geeksforgeeks.org/c-11-vs-c-14-vs-c-17/) 之后)增加的。
因此，现在有三个[参考呼叫](https://www.geeksforgeeks.org/difference-between-call-by-value-and-call-by-reference/)选项-

1.  通过指针。
2.  通过使用左值(普通)引用。
3.  通过使用右值引用(在 C++ 11 中首次引入)。

这里只显示左值和右值引用的所有可能重载。

**注:**
为方便起见， [std::string](https://www.geeksforgeeks.org/stdstring-class-in-c/) 在下面的例子中用作自变量。也可以使用任何其他类型的参数(包括用户定义的类型)。

取左值引用和右值引用的函数的重载-

1.  非常数左值参考。
2.  常量左值参考。
3.  非常数右值引用。
4.  常量右值参考。

**<u>非常数左值参考</u>**

在本例中，[函数](https://www.geeksforgeeks.org/functions-in-c/)接受一个非常量左值引用作为参数，这意味着可以修改所提供的参数。

**语法:**

> void foo(STD::string & str)；//非常数左值引用重载

*   foo()函数接受非常量左值引用作为参数，这意味着可以修改(读/写)提供的参数。
*   可以根据函数签名传递的变量/对象的类型(参见下面的程序)-
    1.  只有命名的可修改对象。(以下程序中的案例 1)。

下面是实现上述方法的 C++ 程序

## C++ 14

```cpp
// C++ program to implement
// the above approach

// for std::cout, std::endl
#include <iostream>

// for std::string
#include <string>

// for EXIT_SUCCESS
#include <cstdlib>

// for std::move()
#include <utility>

// Declaration

// A foo() function takes the
// argument of non-const lvalue
// reference
void foo(std::string& str);

// Driver code
int main()
{
    // Case 1 - A named non-const object
    // non-const object
    std::string namedNonConstObj{
        "This is named non-const object"
    };
    foo(namedNonConstObj);

    // Case 2 - A named const object
    // const object
    const std::string namedConstObject{
        "This is named const object"
    };

    // Error
    // foo(namedConstObject);

    // Case 3 - A unnamed temporary object
    // Error
    // foo(std::string("This is unnamed
    // temporary object"));

    // Case 4 - using std::move() for named
    // non-const object
    std::string namedNonConstObjWithMove{
        "This is named non-const object - using std::move()"
    };

    // Error
    // foo(std::move(namedNonConstObjWithMove));

    // Case 5 - using std::move() for named const object
    const std::string namedConstObjectWithMove{
        "This is named const object - using std::move()"
    };

    // foo(std::move(namedConstObjectWithMove));
    // Error

    /* Case 6 - using std::move() for unnamed 
  // temporary object */
    // foo(std::move(std::string("This is
    // unnamed temporary object - using
    // std::move()")));
    // Error
    return EXIT_SUCCESS;
}

// Definition
void foo(std::string& str)
{
    // do something
    static int counter{ 1 };
    std::cout << counter++ << ". " << str << std::endl;
    // do something
}
```

**Output**

> 1.这被命名为非常数对象