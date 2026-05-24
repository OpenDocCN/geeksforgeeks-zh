# std::string::front()用 c++ 举例

> 原文:[https://www . geeksforgeeks . org/stdstringfront-in-cwith-examples/](https://www.geeksforgeeks.org/stdstringfront-in-cwith-examples/)

此函数返回对字符串第一个字符的直接引用。这只能用于非空字符串。
可以用来访问字符串的第一个字符，也可以在字符串的开头插入一个字符。插入一个字符后，字符串的长度保持不变，第一个字符被新字符替换。

**语法**

```cpp
string str ("GeeksforGeeks");

Accessing first character
char first_char = str.front();

Inserting character at start of string
str.front() = '#';

```

**参数:**该函数不取参数

**返回值:**字符串中第一个字符的引用

**异常:**如果字符串为空，则显示未定义的行为。

以下示例说明了上述方法的使用:

**程序 1:**

```cpp
// C++ program to demonstrate
// the use of the above method

#include <iostream>

// for std::string::front
#include <string>

using namespace std;

int main()
{
    string str("GeeksforGeeks");

    // Accessing first character of string
    char first_char = str.front();

    cout << "First character of string = "
         << first_char << endl;

    // Inserting a character at
    // the start of string
    str.front() = '#';

    cout << "New string = " << str << endl;

    return 0;
}
```

**Output:**

```cpp
First character of string = G
New string = #eeksforGeeks

```

**程序 2:** 当字符串为空时，显示未定义的行为。

```cpp
// C++ program to demonstrate
// the use of the above method

#include <iostream>

// for std::string::front
#include <string>

using namespace std;

int main()
{
    string str(""); // Empty string

    // trying to access first character
    // of an empty string
    char first_char = str.front();

    cout << "First character of string = "
         << first_char << endl;

    // Inserting a character at
    // the start of an empty string
    str.front() = '#';

    cout << "New string = " << str << endl;

    return 0;
}
```

**Output:**

```cpp
First character of string =  
New string =

```

**参考:**T2【STD::string::front()