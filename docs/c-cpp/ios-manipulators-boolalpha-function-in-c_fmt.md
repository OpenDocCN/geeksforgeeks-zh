# C++ 中的 `boolalpha()` 流操纵器

> 原文：[https://www.geeksforgeeks.org/ios-manipulators-boolalpha-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-boolalpha-function-in-c/)

C++ 中的流操纵器 `boolalpha()` 方法用于设置指定字符串流的 `boolalpha` 格式标志。

## 语法

```cpp
ios_base& boolalpha (ios_base& str)
```

## 参数

该方法接受一个 `ios_base` 对象 `str` 作为参数，该参数是受格式标志影响的流。

## 返回值

该方法返回设置了 `boolalpha` 格式标志的 `ios_base` 流对象。

## 示例 1

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

**输出：**

```cpp
boolalpha flag: true
```

## 示例 2

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

**输出：**

```cpp
boolalpha flag: false
```

## 参考

[http://www.cplusplus.com/reference/ios/boolalpha/](http://www.cplusplus.com/reference/ios/boolalpha/)