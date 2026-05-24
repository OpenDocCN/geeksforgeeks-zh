# ios 操纵器在 C++ 中显示()函数

> 原文:[https://www . geesforgeks . org/IOs-机械手-showpos-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-showpos-function-in-c/)

C++ 中**流操纵器**的 **showpos()** 方法用于设置指定字符串流的 showpos 格式标志。此标志始终显示非负值及其+号。

**语法:**

```cpp
ios_base& showpos (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是受格式标志影响的流。

**返回值:**该方法返回设置了 showpos 格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of showpos() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integers
    int a = 10;
    int b = 0;

    // Using showpos()
    cout << "showpos flag: "
         << showpos
         << a << endl
         << b << endl;

    return 0;
}
```

**输出:**

```cpp
showpos flag: +10
+0

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of showpos() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integers
    int a = -10;

    // Using showpos()
    cout << "showpos flag: "
         << showpos
         << a << endl;

    return 0;
}
```

**输出:**

```cpp
showpos flag: -10

```

**参考:**T2】http://www.cplusplus.com/reference/ios/showpos/