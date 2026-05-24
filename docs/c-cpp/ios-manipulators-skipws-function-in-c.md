# ios 操纵器 skipws()函数在 C++ 中

> 原文:[https://www . geeksforgeeks . org/IOs-机械手-skipws-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-skipws-function-in-c/)

C++ 中**流操纵器**的 **skipws()** 方法用于设置指定字符串流的 skipws 格式标志。此标志跳过输入流中第一个非空白字符之前的空白。

**语法:**

```cpp
ios_base& skipws (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是受格式标志影响的流。

**返回值:**该方法返回设置了 skipws 格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of skipws() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

    // Initializing the character
    char a, b, c;

    // Stream input with leading whitespaces
    istringstream iss("        GFG");

    // Using skipws()
    iss >> skipws >> a >> b >> c;

    cout << "skipws flag: "
         << a << endl
         << b << endl
         << c << endl;

    return 0;
}
```

**输出:**

```cpp
skipws flag: G
F
G

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of skipws() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

    // Initializing the character
    char a;

    // Stream input with leading whitespaces
    istringstream iss("        G");

    // Using skipws()
    iss >> skipws >> a;

    cout << "skipws flag: "
         << a << endl;

    return 0;
}
```

**输出:**

```cpp
skipws flag: G

```

**参考:**T2】http://www.cplusplus.com/reference/ios/skipws/