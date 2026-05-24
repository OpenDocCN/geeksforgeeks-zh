# ios操纵器unitbuf()在C++中的功能

> 原文：[https://www.geeksforgeeks.org/ios-manipulators-unitbuf-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-unitbuf-function-in-c/)

C++中`流操纵器`的`unitbuf()`方法用于设置指定字符串流的`unitbuf`格式标志。该标志在每次操作后刷新相关的缓冲区。

## 语法

```cpp
ios_base& unitbuf (ios_base& str)
```

## 参数
该方法接受`字符串`作为参数，该参数是受格式标志影响的流。

## 返回值
该方法返回设置了`unitbuf`格式标志的`流`字符串。

## 例1

```cpp
// C++ code to demonstrate
// the working of unitbuf() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

// Initializing the character
    char a, b, c;

// Stream input with leading whitespaces
    istringstream iss("GFG");

// Using unitbuf()
    // buffer flushed 3 times
    iss >> unitbuf >> a >> b >> c;

cout << "unitbuf flag: "
         << a << endl
         << b << endl
         << c << endl;

return 0;
}
```

## 输出

```cpp
unitbuf flag: G
F
G
```

## 例2

```cpp
// C++ code to demonstrate
// the working of unitbuf() function

#include <iostream>
#include <sstream>

using namespace std;

int main()
{

// Initializing the character
    char a, b, c, d, e;

// Stream input with leading whitespaces
    istringstream iss("GEEKS");

// Using unitbuf()
    // buffer flushed 5 times
    iss >> unitbuf >> a >> b >> c >> d >> e;

cout << "unitbuf flag: "
         << a << endl
         << b << endl
         << c << endl
         << d << endl
         << e << endl;

return 0;
}
```

## 输出

```cpp
unitbuf flag: G
E
E
K
S
```

参考：[http://www.cplusplus.com/reference/ios/unitbuf/](http://www.cplusplus.com/reference/ios/unitbuf/)