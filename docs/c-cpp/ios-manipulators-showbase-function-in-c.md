# ios 操纵器在 C++ 中的 showbase()函数

> 原文:[https://www . geesforgeks . org/IOs-机械手-showbase-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-showbase-function-in-c/)

C++ 中**流操纵器**的 **showbase()** 方法用于设置指定字符串流的 showbase 格式标志。该标志显示整数及其基本前缀。

**语法:**

```cpp
ios_base& showbase (ios_base& str)
```

**参数:**该方法接受**字符串**作为参数，该参数是受格式标志影响的流。

**返回值:**该方法返回设置了 showbase 格式标志的**流**字符串。

**例 1:**

## C++

```cpp
// C++ code to demonstrate
// the working of showbase() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    // Using showbase()
    cout << "showbase flag: "
         << hex
         << showbase
         << num << endl;

    return 0;
}
```

**Output:** 

```cpp
showbase flag: 0x32
```

**例 2:**

## C++

```cpp
// C++ code to demonstrate
// the working of showbase() function

#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    // Using showbase()
    cout << "showbase flag: "
         << oct
         << showbase
         << num << endl;

    return 0;
}
```

**Output:** 

```cpp
showbase flag: 062
```

**参考:**T2http://www.cplusplus.com/reference/ios/showbase/