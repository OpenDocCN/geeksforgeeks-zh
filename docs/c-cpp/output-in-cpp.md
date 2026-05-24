# c++ 中的输出

> 原文:[https://www.geeksforgeeks.org/output-in-cpp/](https://www.geeksforgeeks.org/output-in-cpp/)

在本文中，我们将讨论 [C++ 编程](https://www.geeksforgeeks.org/c-plus-plus/)所需的最基本和最常见的[输入/输出操作](https://www.geeksforgeeks.org/formatted-i-o-in-c/)。C++ 运行在很多平台上，比如 Windows、Linux、Unix、Mac 等。这是 C++ 中处理输出最基本的方法。
[**cout**](https://www.geeksforgeeks.org/cincout-vs-scanfprintf/)经常用于打印输出，即..，在监视器上。预定义对象 cout 是 [iostream 类](https://www.geeksforgeeks.org/c-stream-classes-structure/)的一个实例。对于格式化的输出操作，cout 与[插入运算符](https://www.geeksforgeeks.org/overloading-stream-insertion-operators-c/)一起使用，该运算符被写成**“<”<“**”(即两个“小于”符号)。

**程序 1:**
下面是 C++ 程序演示 **cout** 对象的使用:

## C++

```cpp
// C++ program to demonstrate cout
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Used to display the output
    // to the standard output device
    cout << "GeekforGeeks!";

    return 0;
}
```

**Output:**

```cpp
GeekforGeeks!

```

**注:**

*   **#include** 被称为预处理器指令，用于加载文件。
*   **iostream** 是一个[头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)，包含输入/输出操作(cin 和 cout)的函数。

**程序 2:**
下面是演示一个[操纵器](https://www.geeksforgeeks.org/manipulators-in-c-with-examples/)的 C++ 程序，该操纵器可以与 **cout** 对象一起使用:

## C++

```cpp
// C++ program to demonstrate the
// endl manipulator
#include <iostream>
using namespace std;

// Driver Code
int main()
{

    // Stores the data in a
    // variable str
    char str[] = "Geekforgeeks";

    // Print the output
    cout << " A computer science portal"
         << " for geeks - " << str;

    return 0;
}
```

**Output:**

```cpp
A computer science portal for geeks - Geekforgeeks

```

**程序 3:**

在这个例子中，用户被要求输入他/她的城市名称，当用户输入他/她的城市时，它会将城市名称存储在名称变量中。之后，控制台将打印输出字符串。下面是同样的程序:

## C++

```cpp
// C++ program to illustrate the
// above concept
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Name variable can store
    // upto 30 character
    char name[30];

    // Print the output(asking user
    // to enter city name)
    cout << "Please enter your city name: ";

    // Take input from user and store
    // in name variable
    cin >> name;

    // Print output string including
    // user input data
    cout << "Your city is: "
         << name << endl;

    return 0;
}
```

**输入:**
**输出:**