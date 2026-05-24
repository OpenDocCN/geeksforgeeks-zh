# ios 操纵器 nounitbuf()函数在 C++ 中

> 原文:[https://www . geeksforgeeks . org/IOs-机械手-nonitbuf-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-nounitbuf-function-in-c/)

C++ 中**流操纵器**的**nonitbuf()**方法用于清除指定字符串流的 showbase 格式标志。此标志不会在每次操作后刷新关联的缓冲区。

**语法:**

```cpp
ios_base& nounitbuf (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是要清除格式标志的流。

**返回值:**该方法返回设置了 nounitbuf 格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of nounitbuf() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

    // Initializing the character
    char a, b, c;

    // Stream input with leading whitespaces
    istringstream iss("GFG");

    // Using nounitbuf()
    iss >> nounitbuf >> a >> b >> c;

    cout << "nounitbuf flag: "
         << a << endl
         << b << endl
         << c << endl;

    return 0;
}
```

**输出:**

```cpp
nounitbuf flag: G
F
G

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of nounitbuf() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

    // Initializing the character
    char a, b, c, d, e;

    // Stream input with leading whitespaces
    istringstream iss("GEEKS");

    // Using nounitbuf()
    iss >> nounitbuf >> a >> b >> c >> d >> e;

    cout << "nounitbuf flag: "
         << a << endl
         << b << endl
         << c << endl
         << d << endl
         << e << endl;

    return 0;
}
```

**输出:**

```cpp
nounitbuf flag: G
E
E
K
S

```

**参考:**T2】http://www.cplusplus.com/reference/ios/nounitbuf/