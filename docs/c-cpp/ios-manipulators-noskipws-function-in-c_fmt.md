# C++ 中的 noskipws() 流操纵器

> 原文：[https://www.geeksforgeeks.org/ios-manipulators-noskipws-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-noskipws-function-in-c/)

C++ 中的`noskipws()`流操纵器方法用于清除指定流的`showbase`格式标志。该标志控制是否读取输入流中第一个非空白字符之前的空白字符。

## 语法

```cpp
ios_base& noskipws (ios_base& str)
```

## 参数

该方法接受一个`ios_base`流对象`str`作为参数，该参数是要清除格式标志的流。

## 返回值

该方法返回设置了`noskipws`格式标志的`ios_base`流对象`str`。

## 示例 1

```cpp
// C++ code to demonstrate
// the working of noskipws() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

// Initializing the character
    char a, b, c;

// Stream input with leading whitespaces
    istringstream iss("        GFG");

// Using noskipws()
    iss >> noskipws >> a >> b >> c;

    cout << "noskipws flag: "
         << a << endl
         << b << endl
         << c << endl;

    return 0;
}
```

**输出：**

```
noskipws flag:

```

## 示例 2

```cpp
// C++ code to demonstrate
// the working of noskipws() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

// Initializing the character
    char c;

// Stream input with leading whitespaces
    istringstream iss("        G");

// Using noskipws()
    iss >> noskipws >> c;

    cout << "noskipws flag: "
         << c << endl;

    return 0;
}
```

**输出：**

```
noskipws flag:

```

**参考：** [http://www.cplusplus.com/reference/ios/noskipws/](http://www.cplusplus.com/reference/ios/noskipws/)