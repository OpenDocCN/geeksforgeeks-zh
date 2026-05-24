# std::string::back()用 C++ 举例

> 原文:[https://www . geesforgeks . org/stdstringback-in-c-with-examples/](https://www.geeksforgeeks.org/stdstringback-in-c-with-examples/)

该函数返回对字符串最后一个字符的直接引用。这只能用于非空字符串。
这可用于访问字符串的最后一个字符，以及在字符串末尾追加一个字符。追加一个字符后，字符串的长度保持不变，字符串的最后一个字符被新字符替换

**语法**

```cpp
string str ("GeeksforGeeks");

Accessing last character
char end_char = str.back();

Appending character at end of string
str.back() = '#';

```

**参数:**该函数不取参数

**返回值:**字符串中最后一个字符的引用

**异常:**如果字符串为空，则显示未定义的行为。

以下示例说明了上述方法的使用:

**程序 1:**

```cpp
// C++ program to demonstrate
// the use of the above method

#include <iostream>

// for std::string::back
#include <string>

using namespace std;

int main()
{
    string str("GeeksforGeeks");

    // Accessing last character of string
    char end_char = str.back();

    cout << "Last character of string = "
         << end_char << endl;

    // Appending a character to
    // the end of string
    str.back() = '#';

    cout << "New string = " << str << endl;

    return 0;
}
```

**Output:**

```cpp
Last character of string = s
New string = GeeksforGeek#

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

    // trying to access last character
    // of an empty string
    char end_char = str.back();

    cout << "Last character of string = "
         << end_char << endl;

    // Appending a character to
    // the end of an empty string
    str.back() = '#';

    cout << "New string = " << str << endl;

    return 0;
}
```

**Output:**

```cpp
Last character of string =  
New string =  ÉGÃ          @      ·ùþ?aPé£Îý          @     ?k¯Ã  ÿÿÿÿÿÿÿXé£Îý  ÿÿÿ   
@             Ï?¨Õ,Ä @     Pé£Îý                  Ï??Á±?ðÏ?Ø%Bð
```