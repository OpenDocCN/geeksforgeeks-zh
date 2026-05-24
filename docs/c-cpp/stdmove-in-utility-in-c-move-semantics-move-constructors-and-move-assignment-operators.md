# STD::c++ 中的移动工具|移动语义、移动构造函数和移动赋值运算符

> 原文:[https://www . geesforgeks . org/stdmove-in-utility-in-c-move-semantics-move-constructor-and-move-assignment-operator/](https://www.geeksforgeeks.org/stdmove-in-utility-in-c-move-semantics-move-constructors-and-move-assignment-operators/)

**先决条件:**

1.  [lvalue 参考](https://www.geeksforgeeks.org/lvalues-references-and-rvalues-references-in-c-with-examples/)
2.  [右值参考](https://www.geeksforgeeks.org/understanding-lvalues-prvalues-and-xvalues-in-ccwith-examples/)
3.  [复制语义(复制构造器)](https://www.geeksforgeeks.org/copy-constructor-vs-assignment-operator-in-c/)

**参考文献:**

在 C++ 中有两种类型的引用-

1.  左值参考:
    *   左值是将出现在赋值的左侧或右侧的表达式。
    *   简单来说，就是一个有名字和内存地址的变量或对象。
    *   它使用一个&符号。
2.  右值参考:
    *   右值是仅出现在赋值的右侧的表达式。
    *   变量或对象只有一个内存地址(临时对象)。
    *   它使用两个&符号。

**移动构造函数和语义:**

[移动构造器](https://www.geeksforgeeks.org/move-constructors-in-c-with-examples/)是在 [C++ 11](https://www.geeksforgeeks.org/c-11-vs-c-14-vs-c-17/) 中引入的。移动构造函数的需要或目的是尽可能快地从源(原始)[对象](https://www.geeksforgeeks.org/c-classes-and-objects/)中窃取或移动尽可能多的资源，因为源不再需要有有意义的值，和/或因为它无论如何都会在一瞬间被销毁。从而可以避免不必要地创建对象的副本，并有效利用资源

虽然可以窃取资源，但必须使源(原始)对象保持有效状态，以便能够正确销毁。

> 移动构造函数通常会“窃取”源(原始)对象的资源，而不是复制它们，并使源对象处于“有效但未指定的状态”。

复制构造函数使用用一个&符号标记的左值引用，而移动构造函数使用用两个&符号标记的右值引用。

> [std::move()](https://www.geeksforgeeks.org/stdmove-in-c/) 是用于将左值引用转换为右值引用的函数。用于将资源从源对象移出，即用于将资源从一个对象高效转移到另一个对象。
> 
> std::move()在 [<实用工具>标题](https://www.geeksforgeeks.org/utility-in-c/)中定义。

**语法:**

> *   模板
>     字号 STD::remove _ reference<T>:type&T5】move(T&&T)不例外；（从 C++ 11 开始)(直到 C++ 14)
> *   模板
>     const expr STD::remove _ reference _ T<T>&T21】移动(T & & T)无例外（从 C++ 14 开始)

**示例:**下面是 C++ 程序，展示了在不使用移动语义的情况下，即在 C++ 11 之前发生的情况。

## C++ 14

```cpp
// C++ program to implement
// the above approach

// for std::string
#include <string>

// for std::cout
#include <iostream>

// for EXIT_SUCCESS macro
#include <cstdlib>

// for std::vector
#include <vector>

// for std::move()
#include <utility>

// Declaration
std::vector<std::string> createAndInsert();

// Driver code
int main()
{
    // Constructing an empty vector
    // of strings
    std::vector<std::string> vecString;

    // calling createAndInsert() and
    // initializing the local vecString
    // object
    vecString = createAndInsert();

    // Printing content of the vector
    for (const auto& s : vecString) {
        std::cout << s << '\n';
    }

    return EXIT_SUCCESS;
}

// Definition
std::vector<std::string> createAndInsert()
{
    // constructing a vector of
    // strings with an size of
    // 3 elements
    std::vector<std::string> vec;
    vec.reserve(3);

    // constructing & initializing
    // a string with "Hello"
    std::string str("Hello");

    // Inserting a copy of string
    // object
    vec.push_back(str);

    // Inserting a copy of an
    // temporary string object
    vec.push_back(str + str);

    // Again inserting a copy of
    // string object
    vec.push_back(std::move(str));

    // Finally, returning the local
    // vector
    return vec;
}
```

**Output**

```cpp
Hello
HelloHello
Hello
```

**说明:**

假设程序是使用不支持移动语义的编译器编译和执行的。在 main()函数中，

**1。STD::vector<STD::string>vector string；-** 创建一个没有元素的空向量。
T3】2。vectring = createdinsert()；- 调用 createAndInsert()函数。
3。在 createAndInsert()函数中-

*   **STD::string str(" Hello ")；-** 创建另一个名为 vec 的新空向量。
*   **vec . reserve(3)；-** 保留 3 个元素的大小。
*   **STD::string str(" Hello ")；-** 一个名为字符串的字符串，用“Hello”初始化。
*   **vec . push _ back(str)；-** 字符串通过值传递到向量向量。因此，通过调用 String 类的复制构造函数，将创建 str 的(深度)副本并将其插入到 vec 中。
*   **vec . push _ back(str+str)；-** 这是一个三阶段的过程-
    1.  将创建一个临时对象(str + str)，它有自己的独立内存。
    2.  这个临时对象被插入到 vector vec 中，vector vec 再次通过值传递，这意味着将创建临时字符串对象的(深度)副本。
    3.  从现在开始，临时对象不再需要，因此它将被销毁。

**注意:**这里，我们不必要地分配&解除分配临时字符串对象的内存。只需将数据从源对象中移出，就可以进一步优化(改进)。

*   **vec . push _ back(str)；-** 执行与 5 号线相同的流程。请记住，此时 str 字符串对象将是最后使用的。
*   **返回 vec-** 这是 createAndInsert()函数的结尾-
    *   首先，字符串对象 str 将被销毁，因为范围被留在它被声明的地方。
    *   其次，返回字符串的局部向量，即 vec。因为函数的返回类型不是由引用定义的。因此，整个向量的深层副本将通过在单独的内存位置分配来创建，然后销毁本地向量对象，因为作用域留在声明它的地方。
    *   最后，字符串向量的副本将返回给调用者 main()函数。
*   最后，在返回到调用者 main()函数后，简单地打印局部 vecString 向量的元素。

**示例:**下面是使用移动语义实现上述概念的 C++ 程序，即从 C++ 11 及更高版本开始。

## C++ 14

```cpp
// C++ program to implement
// the above approach

// for std::string
#include <string>

// for std::cout
#include <iostream>

// for EXIT_SUCCESS macro
#include <cstdlib>

// for std::vector
#include <vector>

// for std::move()
#include <utility>

// Declaration
std::vector<std::string> createAndInsert();

// Driver code
int main()
{
    // Constructing an empty vector
    // of strings
    std::vector<std::string> vecString;

    // calling createAndInsert() and
    // initializing the local vecString
    // object
    vecString = createAndInsert();

    // Printing content of the vector
    for (const auto& s : vecString) {
        std::cout << s << '\n';
    }

    return EXIT_SUCCESS;
}

// Definition
std::vector<std::string> createAndInsert()
{
    // constructing a vector of
    // strings with an size of
    // 3 elements
    std::vector<std::string> vec;
    vec.reserve(3);

    // constructing & initializing
    // a string with "Hello"
    std::string str("Hello");

    // Inserting a copy of string
    // object
    vec.push_back(str);

    // Inserting a copy of an
    // temporary string object
    vec.push_back(str + str);

    // Again inserting a copy of
    // string object
    vec.push_back(std::move(str));

    // Finally, returning the local
    // vector
    return vec;
}
```

**Output**

```cpp
Hello
HelloHello
Hello
```

**说明:**

这里，为了使用移动语义。编译器必须支持 C++ 11 标准或以上。 **main()** 函数和**createdandsert()**函数的执行故事保持不变，直到行**vec . push _ back(str)；**

可能会出现一个问题，为什么临时对象没有使用 std::move()移动到 vector vec。背后的原因是向量的 push_back()方法。从 C++ 11 开始， [push_back()](https://en.cppreference.com/w/cpp/container/vector/push_back) 方法被提供了新的重载版本。

**语法:**

> 1.  const expr void push _ back(const T&值);（自 c++ 20)
> 
> 2.  void push _ back(const T&值);（直到 c++ 20)
> 3.  const expr void push _ back(T & amp 值);（自 C++ 20 起)

*   **vec . push _ back(str+str)；-**
    1.  将创建一个临时对象(str + str)，它有自己单独的内存，并将调用重载的 push_back()方法(第二版或第四版取决于 C++ 的版本)，该方法将从临时源对象(str + str)窃取(或移动)数据到向量 vec 中，因为它不再需要。
    2.  执行移动后，临时对象被销毁。因此，它不是调用复制构造函数(复制语义)，而是通过复制字符串的大小和操作指向数据内存的指针来优化。
    3.  在这里，需要注意的重要一点是，我们利用的内存很快将不再拥有它的内存。换句话说，我们以某种方式优化了它。这都是因为右值引用和移动语义。
*   **vec . push _ back(STD::move(str))；-** 这里明确提示编译器 ***【对象不再需要】*** 命名为 str ( *左值引用*)借助 [std::move()](https://www.geeksforgeeks.org/stdmove-in-c/) 函数通过将左值引用转换为右值引用，str 的资源将被移动到向量中。那么 str 的状态就变成了“有效但未指定的状态”。这对我们来说并不重要，因为这是我们最后一次使用，而且很快就会被摧毁。
*   最后，将名为 vec 的字符串的局部向量返回给调用者。
*   最后，返回到调用者 main()函数，并简单地打印本地 vectstring**向量的元素。**

**将 vec 对象返回给调用者时可能会出现问题。由于不再需要它，并且向量的整个临时对象将被创建，并且局部向量向量将被销毁，那么为什么 std::move()不被用来窃取值并返回它。
它的答案简单明了，有编译器层面的优化称为(命名)返回值对象，更通俗的说法是 [RVO](https://www.geeksforgeeks.org/copy-elision-in-c/) 。**

****移动语义的一些后退:****

1.  **在 const 对象上调用 std::move()通常没有效果。

    *   窃取或移动 const 对象的资源没有任何意义。
    *   参见下面程序中的 **constObjectCallFunc()函数**** 
2.  **当且仅当支持复制语义时，复制语义用作移动语义的后备。

    *   参见下面程序中的 **baz()功能**** 
3.  **如果没有将右值引用作为参数的实现，将使用普通的常量左值引用。

    *   参见下面程序中的 **baz()** 功能** 
4.  **如果缺少以右值引用作为参数的函数或方法&以常量左值引用作为参数。然后会产生编译时错误。

    *   参见下面程序中的**条()功能**** 

****注意:****foo()函数**有所有必要类型的参数。**

**下面是实现上述所有概念的 C++ 程序-**

## **C++ 14**

```cpp
// C++ program to implement
// the above concept

// for std::cout & std::endl
#include <iostream>

// for std::move()
#include <utility>

// for std::string
#include <string>

// for EXIT_SUCCESS macro
#include <cstdlib>

// foo() taking a non-const lvalue
// reference argument
void foo(std::string& str);

// foo() taking a const lvalue
// reference argument
void foo(const std::string& str);

// foo() taking a rvalue
// reference argument
void foo(std::string&& str);

// baz() taking a const lvalue
// reference argument
void baz(const std::string& str);

// baz() taking a non-const lvalue
// reference argument
void baz(std::string& str);

// bar() taking a non-const lvalue
// reference argument
void bar(std::string& str);

// constObjectCallFunc() taking a
// rvalue reference argument
void constObjectCallFunc(std::string&& str);

// Driver code
int main()
{
    // foo(std::string&& str) will
    // be called
    foo(std::string("Hello"));

    std::string goodBye("Good Bye!");

    // foo(std::string& str) will be called
    foo(goodBye);

    // foo(std::string&& str) will be called
    foo(std::move(goodBye + " using std::move()"));

    std::cout << "\n\n\n";

    // move semantics fallback
    // baz(const std::string& str) will be called
    baz(std::string("This is temporary string object"));

    // baz(const std::string& str) will be called
    baz(std::move(std::string(
        "This is temporary string object using std::move()")));

    std::cout << "\n\n\n";

    std::string failToCall("This will fail to call");

    /*
      Reasons to fail bar() call -
          1\. No rvalue reference implementation
           available         // First Preference
          2\. No const lvalue reference implementation
           available    // Second Preference
          3\. Finally fails to invoke bar() function
      */
    // bar(std::move(failToCall));
    // Error : check the error message for more
    // better understanding
    std::cout << "\n\n\n";

    const std::string constObj(
        "Calling a std::move() on a const object usually has no effect.");
    // constObjectCallFunc(std::move(constObj));
    // Error : because of const qualifier
    // It doesn't make any sense to steal or
    // move the resources of a const object

    return EXIT_SUCCESS;
}

void foo(const std::string& str)
{
    // do something
    std::cout << "foo(const std::string& str) : "
              << "\n\t" << str << std::endl;
}

void foo(std::string& str)
{
    // do something
    std::cout << "foo(std::string& str) : "
              << "\n\t" << str << std::endl;
}

void foo(std::string&& str)
{
    // do something
    std::cout << "foo(std::string&& str) : "
              << "\n\t" << str << std::endl;
}

void baz(const std::string& str)
{
    // do something
    std::cout << "baz(const std::string& str) : "
              << "\n\t" << str << std::endl;
}

void baz(std::string& str)
{
    // do something
    std::cout << "baz(std::string& str) : "
              << "\n\t" << str << std::endl;
}

void bar(std::string& str)
{
    // do something
    std::cout << "bar(std::string&& str) : "
              << "\n\t" << str << std::endl;
}

void constObjectCallFunc(std::string&& str)
{
    // do something
    std::cout << "constObjectCallFunc(std::string&& str) : "
              << "\n\t" << str << std::endl;
}
```

****Output**

```cpp
foo(std::string&& str) : 
    Hello
foo(std::string& str) : 
    Good Bye!
foo(std::string&& str) : 
    Good Bye! using std::move()

baz(const std::string& str) : 
    This is temporary string object
baz(const std::string& str) : 
    This is temporary string object using std::move()
```** 

****总结:****

*   **移动语义允许我们优化对象的复制，在那里我们不需要价值。它通常隐式使用(对于未命名的临时对象或局部返回值)，或者与 std::move()一起显式使用。**
*   **std::move()的意思是 ***“不再需要这个值”*** **。****
*   **标有 std::move()的对象永远不会被部分销毁。即[析构器](https://www.geeksforgeeks.org/destructors-c/)将被调用来适当地破坏对象。**