# 线路控制指令

> 原文:[https://www.geeksforgeeks.org/line-control-directive/](https://www.geeksforgeeks.org/line-control-directive/)

[**<u>【线路控制指令】</u>**](https://www.geeksforgeeks.org/cpp-preprocessor-directives-set-2/) **:** 每当编译一个程序时，都有可能在程序中出现一些错误。每当编译器识别出程序中的一个错误时，它都会向我们提供发现错误的文件名以及行的列表和错误所在的确切行号。这使得我们很容易发现并纠正错误。但是，编译器在编译错误期间应该提供什么信息可以使用 **#line** 指令来控制。它操纵[编译器](https://www.geeksforgeeks.org/compiling-with-g-plus-plus/)读取一行，以便程序员可以控制该行以及[文件](https://www.geeksforgeeks.org/file-handling-c-classes/)编译器读取的行。基本上是用来重置行号的。

**<u>特征</u> :**

*   A [C](https://www.geeksforgeeks.org/c-programming-language/) / [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 源代码实际上是[预处理](https://www.geeksforgeeks.org/cc-preprocessors/)创建一个翻译单元，然后编译。
*   一个翻译单元有[头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)及其本身的所有内容。因此，对于编译器来说，很难区分文件和它正在读取的行，然后它会相应地生成[错误](https://www.geeksforgeeks.org/errors-in-cc/)消息。
*   对于预处理器，它每次都添加行控制，并将头文件插入源代码。

**<u>语法</u> :**

> **语法 1**
> #行号“文件名”
> 
> **语法 2**
> #行号“文件名”
> 
> **行号** —将分配给下一个代码行的行号。从这一点开始，连续行的行号将一个接一个地增加。
> 
> **“文件名”** —可选参数，允许重新定义将要显示的文件名。

**说明:**

*   以上两种[语法](https://www.geeksforgeeks.org/c-programming-basics/)都是一样的，只是略有不同。
*   **语法-1** 将由编译器读取，而**语法 2** 将由预处理器读取。
*   最终**语法-2** 将在翻译单元中转换为**语法 1** 。
*   这些语法最终告诉编译器，下一行的行号为**“行号”**，属于文件**“文件名”**。
*   要验证这一点，请使用两个内置的[宏](https://www.geeksforgeeks.org/macros-and-its-types-in-c-cpp/):
    *   **__LINE__:** 它打印源代码内部的行号。
    *   **__FILE__:** 它打印源代码的文件名。

下面是演示线路控制的程序:

## C++

```cpp
// C++ program to demonstrate line control
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    cout << "START" << endl;

    cout << __LINE__ << " "
         << __FILE__ << endl;

#line 67 "Binod.cpp"

    cout << __LINE__
         << " " << __FILE__
         << endl; // (67)

    // This will apply continuously (68)
    cout << __LINE__ << endl; // (69)
}
```

**Output:** 

START
11/usr/share/IDE _ PROGRAMS/c++/other/1d 6323581 EEA 236 f 68331 bcde 745 F2 C 6/1d 6323581 EEA 236 f 68331 bcde 745 F2 C 6 . CPP
68 binod . CPP
73