# c++ 中的异常处理

> 原文:[https://www.geeksforgeeks.org/exception-handling-c/](https://www.geeksforgeeks.org/exception-handling-c/)

C++ 相对于 C 的优势之一是异常处理。异常是程序在执行过程中遇到的运行时异常或异常情况。有两种类型的异常:a)同步的，b)异步的(例如:超出程序控制的，磁盘故障等)。C++ 为此提供了以下专门的关键字。
*try* :代表一个可以抛出异常的代码块。
*catch* :表示抛出特定异常时执行的代码块。
*抛出*:用于抛出异常。也用于列出函数抛出但不处理自身的异常。

**为什么是异常处理？**
以下是异常处理相对于传统错误处理的主要优势。

***1)** 错误处理代码与正常代码的分离:*在传统的错误处理代码中，总是有 if else 条件来处理错误。这些条件和处理错误的代码与正常流程混淆了。这使得代码可读性和可维护性降低。使用 try catch 块，用于错误处理的代码与正常流程分离。

***2)** 函数/方法可以处理它们选择的任何异常:*一个函数可以抛出许多异常，但可能会选择处理其中的一些。其他抛出但没有被捕获的异常可以由调用者处理。如果调用者选择不捕捉它们，那么异常将由调用者的调用者处理。
在 C++ 中，函数可以使用 throw 关键字指定它抛出的异常。这个函数的调用方必须以某种方式处理异常(要么再次指定它，要么捕获它)

***3)** 错误类型的分组:*在 C++ 中，基本类型和对象都可以作为异常抛出。我们可以创建异常对象的层次结构，在名称空间或类中对异常进行分组，根据类型对它们进行分类。

**C++ 异常:**

在执行 C++ 代码时，可能会出现不同的错误:程序员的编码错误、错误输入导致的错误或其他不可预见的事情。

当发生错误时，C++ 通常会停止并生成错误消息。这个的技术术语是:C++ 将抛出一个异常(抛出一个错误)。

**C++ 试捕:**

C++ 中的异常处理由三个关键词组成:尝试、抛出和捕获:

try 语句允许您定义一个代码块，在执行该代码块时对其进行错误测试。

throw 关键字在检测到问题时引发异常，这让我们可以创建一个自定义错误。

catch 语句允许您在 try 块中出现错误时定义要执行的代码块。

尝试和捕捉关键字成对出现:

我们使用 try 块来测试一些代码:如果 age 变量小于 18，我们将抛出一个异常，并在 catch 块中处理它。

在 catch 块中，我们捕获错误并对其采取措施。catch 语句接受一个参数:在我们的示例中，我们使用了一个 int 变量(myNum)(因为我们在 try 块(age)中抛出了一个 int 类型的异常)，以输出 age 的值。

如果没有出现错误(例如，如果年龄是 20 岁而不是 15 岁，这意味着年龄将大于 18 岁)，则跳过 catch 块:

**c++ 中的异常处理**

**1)** 下面是一个简单的例子，展示 C++ 中的异常处理。程序的输出解释了 try/catch 块的执行流程。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

int main()
{
   int x = -1;

   // Some code
   cout << "Before try \n";
   try {
      cout << "Inside try \n";
      if (x < 0)
      {
         throw x;
         cout << "After throw (Never executed) \n";
      }
   }
   catch (int x ) {
      cout << "Exception Caught \n";
   }

   cout << "After catch (Will be executed) \n";
   return 0;
}
```

**输出:**

```cpp
Before try
Inside try
Exception Caught
After catch (Will be executed)
```

**2)** 有一个叫做‘catch all’catch(…)的特殊 catch 块，可以用来捕获所有类型的异常。例如，在下面的程序中，一个 int 作为异常被抛出，但是没有针对 int 的 catch 块，所以 catch(…)块将被执行。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

int main()
{
    try  {
       throw 10;
    }
    catch (char *excp)  {
        cout << "Caught " << excp;
    }
    catch (...)  {
        cout << "Default Exception\n";
    }
    return 0;
}
```

**输出:**

```cpp
Default Exception
```

**3)** 对于基元类型，隐式类型转换不会发生。例如，在下面的程序中,“a”没有隐式转换为 int

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

int main()
{
    try  {
       throw 'a';
    }
    catch (int x)  {
        cout << "Caught " << x;
    }
    catch (...)  {
        cout << "Default Exception\n";
    }
    return 0;
}
```

**输出:**

```cpp
Default Exception
```

**4)** 如果抛出异常，并且没有在任何地方捕获到，则程序异常终止。例如，在下面的程序中，抛出了一个 char，但是没有 catch 块来捕获 char。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

int main()
{
    try  {
       throw 'a';
    }
    catch (int x)  {
        cout << "Caught ";
    }
    return 0;
}
```

**输出:**

```cpp
terminate called after throwing an instance of 'char'

This application has requested the Runtime to terminate it in an 
unusual way. Please contact the application's support team for 
more information.
```

我们可以通过[编写自己的意外函数](http://publib.boulder.ibm.com/infocenter/lnxpcomp/v8v101/index.jsp?topic=%2Fcom.ibm.xlcpp8l.doc%2Flanguage%2Fref%2Fcplr162.htm)来改变这种异常终止行为。
**5)** 派生类异常应该在基类异常之前被捕获。详见[本](https://www.geeksforgeeks.org/g-fact-60/)。
**6)** 和 Java 一样，C++ 库有一个[标准异常类](http://www.cplusplus.com/reference/exception/exception/)，它是所有标准异常的基类。标准库的组件抛出的所有对象都是从这个类派生的。因此，所有的标准异常都可以通过捕捉这种类型
**7)** 来捕捉，不像 Java，在 C++ 中，所有的异常都是不检查的。编译器不检查是否捕捉到异常(详见[本](https://www.geeksforgeeks.org/checked-vs-unchecked-exceptions-in-java/))。例如，在 C++ 中，没有必要在函数声明中指定所有未捕获的异常。尽管建议这样做。例如，下面的程序编译良好，但是理想情况下 fun()的签名应该列出未检查的异常。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

// This function signature is fine by the compiler, but not recommended.
// Ideally, the function should specify all uncaught exceptions and function
// signature should be "void fun(int *ptr, int x) throw (int *, int)"
void fun(int *ptr, int x)
{
    if (ptr == NULL)
        throw ptr;
    if (x == 0)
        throw x;
    /* Some functionality */
}

int main()
{
    try {
       fun(NULL, 0);
    }
    catch(...) {
        cout << "Caught exception from fun()";
    }
    return 0;
}
```

**输出:**

```cpp
Caught exception from fun()
```

编写上述代码的更好方法

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

// Here we specify the exceptions that this function
// throws.
void fun(int *ptr, int x) throw (int *, int) // Dynamic Exception specification
{
    if (ptr == NULL)
        throw ptr;
    if (x == 0)
        throw x;
    /* Some functionality */
}

int main()
{
    try {
       fun(NULL, 0);
    }
    catch(...) {
        cout << "Caught exception from fun()";
    }
    return 0;
}
```

(**注:**动态异常规范的使用在 C++ 11 之后已经被弃用，其中一个原因可能是因为它可以随机中止你的程序。当您抛出动态异常规范中没有提到的另一种类型的异常时，可能会发生这种情况，因为在这种情况下，程序调用(直接)terminate()，默认情况下调用 abort())。

**输出:**

```cpp
Caught exception from fun()
```

**8)** 在 C++ 中，可以嵌套 try-catch 块。此外，可以使用“抛出”重新抛出异常

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

int main()
{
    try {
        try {
            throw 20;
        }
        catch (int n) {
            cout << "Handle Partially ";
            throw; // Re-throwing an exception
        }
    }
    catch (int n) {
        cout << "Handle remaining ";
    }
    return 0;
}
```

**输出:**

```cpp
Handle Partially Handle remaining
```

一个函数也可以使用相同的“throw；。一个函数可以处理一个部分，并可以要求调用者处理剩余部分。
**(9)**当抛出异常时，在控制转移到 catch 块之前，在封闭 try 块内创建的所有对象都被析构。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

class Test {
public:
    Test() { cout << "Constructor of Test " << endl; }
    ~Test() { cout << "Destructor of Test " << endl; }
};

int main()
{
    try {
        Test t1;
        throw 10;
    }
    catch (int i) {
        cout << "Caught " << i << endl;
    }
}
```

**输出:**

```cpp
Constructor of Test
Destructor of Test
Caught 10
```

**10)** 你可以试试[c++ 异常处理小测验](https://www.geeksforgeeks.org/c-plus-plus-gq/exception-handling-gq/)。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。