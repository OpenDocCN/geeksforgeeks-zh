# C++中的`scientific()`流操纵器

> 原文：[https://www.geeksforgeeks.org/ios-manipulators-scientific-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-scientific-function-in-c/)

C++中的流操纵器`scientific()`方法用于设置指定字符串流的`floatfield`格式标志。此标志将浮点字段设置为科学记数法。这意味着，浮点值将被写入科学符号。

## 语法

```cpp
ios_base& scientific (ios_base& str)
```

## 参数

该方法接受`ios_base& str`作为参数，该参数是受格式标志影响的流。

## 返回值

该方法返回设置了内部格式标志的流`str`。

## 例 1

```cpp
// C++ code to demonstrate
// the working of scientific() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the float values
    double x = 1.23;

    cout.precision(5);

    cout << "without scientific flag: "
         << x << endl;

// Using scientific()
    cout << "with scientific flag: "
         << scientific << x << endl;

    return 0;
}
```

**输出：**

```cpp
without scientific flag: 1.23
with scientific flag: 1.23000e+00
```

## 例 2

```cpp
// C++ code to demonstrate
// the working of scientific() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the float values
    double x = 1.0;

    cout.precision(5);

    cout << "without scientific flag: "
         << x << endl;

// Using scientific()
    cout << "with scientific flag: "
         << scientific << x << endl;

    return 0;
}
```

**输出：**

```cpp
without scientific flag: 1
with scientific flag: 1.00000e+00
```

## 例 3

```cpp
// C++ code to demonstrate
// the working of scientific() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the float values
    double x = 1.23e9;

    cout.precision(5);

    cout << "without scientific flag: "
         << x << endl;

// Using scientific()
    cout << "with scientific flag: "
         << scientific << x << endl;

    return 0;
}
```

**输出：**

```cpp
without scientific flag: 1.23e+09
with scientific flag: 1.23000e+09
```

参考：[http://www.cplusplus.com/reference/ios/scientific/](http://www.cplusplus.com/reference/ios/scientific/)