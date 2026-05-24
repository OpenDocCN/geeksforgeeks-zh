# ios 操纵器 boolalpha()在 C++ 中的功能

> 原文:[https://www . geesforgeks . org/IOs-机械手-boolalpha-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-boolalpha-function-in-c/)

C++ 中**流操纵器**的 **boolalpha()** 方法用于设置指定字符串流的 boolalpha 格式标志。

**语法:**

```cpp
ios_base& boolalpha (ios_base& str)

```

**参数:**该方法接受**字符串**作为参数，该参数是受格式标志影响的流。

**返回值:**该方法返回设置了 boolalpha 格式标志的**流**字符串。

**例 1:**

```cpp
// C++ code to demonstrate
// the working of boolalpha() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the boolean flag
    bool flag = true;

    // Using boolalpha()
    cout << "boolalpha flag: "
         << boolalpha << flag << endl;

    return 0;
}
```

**输出:**

```cpp
boolalpha flag: true

```

**例 2:**

```cpp
// C++ code to demonstrate
// the working of boolalpha() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the boolean flag
    bool flag = false;

    // Using boolalpha()
    cout << "boolalpha flag: "
         << boolalpha << flag << endl;

    return 0;
}
```

**输出:**

```cpp
boolalpha flag: false

```

**参考:**T2】http://www.cplusplus.com/reference/ios/boolalpha/