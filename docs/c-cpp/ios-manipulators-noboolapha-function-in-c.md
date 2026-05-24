# ios 操纵器 noboolapha()函数在 C++ 中

> 原文:[https://www . geeksforgeeks . org/IOs-机械手-nopoolapha-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-noboolapha-function-in-c/)

C++ 中**流操纵器**的**nobolalpha()**方法用于获取指定字符串流的 boolapha 格式标志的整数值。

**语法:**

```cpp
ios_base& noboolalpha (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是为其提取格式标志的流。

**返回值:**该方法返回带有 noboolalpha 格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of noboolalpha() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the boolean flag
    bool flag = true;

    // Using noboolalpha()
    cout << "noboolalpha flag: "
         << noboolalpha << flag << endl;

    return 0;
}
```

**输出:**

```cpp
noboolalpha flag: 1

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of noboolalpha() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the boolean flag
    bool flag = false;

    // Using noboolalpha()
    cout << "noboolalpha flag: "
         << noboolalpha << flag << endl;

    return 0;
}
```

**输出:**

```cpp
noboolalpha flag: 0

```

**参考:**T2】http://www.cplusplus.com/reference/ios/noboolalpha/