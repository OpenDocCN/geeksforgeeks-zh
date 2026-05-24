# ios 操纵器在 C++ 中的 showpoint()函数

> 原文:[https://www . geesforgeks . org/IOs-机械手-showpoint-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-showpoint-function-in-c/)

C++ 中**流操纵器**的**显示点()**方法用于设置指定字符串流的显示点格式标志。此标志始终显示浮点值及其十进制值。

**语法:**

```cpp
ios_base& showpoint (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是受格式标志影响的流。

**返回值:**该方法返回设置了显示点格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of showpoint() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the floating values
    double n1 = 10;
    double n2 = 20.0;

    cout.precision(5);

    // Using showpoint()
    cout << "showpoint flag: "
         << showpoint
         << n1 << endl
         << n2 << endl;

    return 0;
}
```

**输出:**

```cpp
showpoint flag: 10.000
20.000

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of showpoint() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the floating values
    double n3 = 30.1223;

    cout.precision(5);

    // Using showpoint()
    cout << "showpoint flag: "
         << showpoint
         << n3 << endl;

    return 0;
}
```

**输出:**

```cpp
showpoint flag: 30.122

```

**参考:**T2】http://www.cplusplus.com/reference/ios/showpoint/