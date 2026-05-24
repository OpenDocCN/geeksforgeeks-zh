# ios 操纵器 noshowpos()在 C++ 中运行

> 原文:[https://www . geeksforgeeks . org/IOs-机械手-noshowpos-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-noshowpos-function-in-c/)

C++ 中**流操纵器**的 **noshowpos()** 方法用于清除指定字符串流的 showbase 格式标志。此标志显示不带+号的非负整数值。

**语法:**

```cpp
ios_base& noshowpos (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是要清除格式标志的流。

**返回值:**该方法返回设置了 noshowpos 格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of noshowpos() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integers
    int a = 10;
    int b = 0;

    // Using noshowpos()
    cout << "noshowpos flag: "
         << noshowpos
         << a << endl
         << b << endl;

    return 0;
}
```

**输出:**

```cpp
noshowpos flag: 10
0

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of noshowpos() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integers
    int a = -10;

    // Using noshowpos()
    cout << "noshowpos flag: "
         << noshowpos
         << a << endl;

    return 0;
}
```

**输出:**

```cpp
noshowpos flag: -10

```

**参考:**T2】http://www.cplusplus.com/reference/ios/noshowpos/