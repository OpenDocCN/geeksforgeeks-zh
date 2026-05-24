# ios 操纵器 nouppercase()函数在 C++ 中

> 原文:[https://www . geeksforgeeks . org/IOs-机械手-noupercase-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-nouppercase-function-in-c/)

C++ 中**流操纵器**的**noupperace()**方法用于清除指定字符串流的 showbase 格式标志。该标志使输出操作不使用大写字母代替小写字母。

**语法:**

```cpp
ios_base& nouppercase (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是要清除格式标志的流。

**返回值:**该方法返回设置了无格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of nouppercase() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

    // Initializing the character
    char a, b, c;

    // Stream input with leading whitespaces
    istringstream iss("gfg");

    // Using nouppercase()
    iss >> a >> b >> c;

    cout << "nouppercase flag: "
         << nouppercase
         << a << endl
         << b << endl
         << c << endl;

    return 0;
}
```

**输出:**

```cpp
nouppercase flag: g
f
g

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of nouppercase() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the int
    int n = 20;

    // Using nouppercase()
    cout << "nouppercase flag: "
         << showbase << hex
         << nouppercase
         << n << endl;

    return 0;
}
```

**输出:**

```cpp
nouppercase flag: 0x14

```

**参考:**T2】http://www.cplusplus.com/reference/ios/nouppercase/