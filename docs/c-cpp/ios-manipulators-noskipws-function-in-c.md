# ios 操纵器 noskipws()在 C++ 中的功能

> 原文:[https://www . geeksforgeeks . org/IOs-机械手-noskipws-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-noskipws-function-in-c/)

C++ 中**流操纵器**的 **noskipws()** 方法用于清除指定字符串流的 showbase 格式标志。该标志读取输入流中第一个非空白字符之前的空白。

**语法:**

```cpp
ios_base& noskipws (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是要清除格式标志的流。

**返回值:**该方法返回设置了 noskipws 格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of noskipws() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

    // Initializing the character
    char a, b, c;

    // Stream input with leading whitespaces
    istringstream iss("        GFG");

    // Using noskipws()
    iss >> noskipws >> a >> b >> c;

    cout << "noskipws flag: "
         << a << endl
         << b << endl
         << c << endl;

    return 0;
}
```

**输出:**

```cpp
noskipws flag:

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of noskipws() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

    // Initializing the character
    char c;

    // Stream input with leading whitespaces
    istringstream iss("        G");

    // Using noskipws()
    iss >> noskipws >> c;

    cout << "noskipws flag: "
         << c << endl;

    return 0;
}
```

**输出:**

```cpp
noskipws flag:

```

**参考:**T2】http://www.cplusplus.com/reference/ios/noskipws/