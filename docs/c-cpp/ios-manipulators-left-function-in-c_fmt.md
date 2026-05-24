# ios 操纵器左()功能在 C++ 中

> 原文: [https://www.geeksforgeeks.org/ios-manipulators-left-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-left-function-in-c/)

C++ 中**流操纵器**的 `left()` 方法用于为指定的字符串流设置 `adjustfield` 格式标志。该标志将 `adjustfield` 设置为左侧。这意味着输出中的数字将通过在末尾插入填充字符来填充到字段宽度。

## 语法:
```
ios_base& left (ios_base& str)
```

## 参数:
该方法接受 `ios_base& str` 作为参数，该参数是受格式标志影响的流。

## 返回值:
该方法返回设置了内部格式标志的 `ios_base& str` 流。

## 例 1:
```cpp
// C++ code to demonstrate
// the working of left() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the integer
    double x = -1.23;

    cout.precision(5);

// Using left()
    cout << "left flag: ";

    cout.width(12);
    cout << left << x << endl;

    return 0;
}
```

## 输出:
```
left flag: -1.23
```

## 例 2:
```cpp
// C++ code to demonstrate
// the working of left() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the integer
    double x = -1.23;

    cout.precision(5);

// Using left()
    cout << "left flag: ";

    cout.width(12);
    cout << left << x << endl;

    return 0;
}
```

## 输出:
```
left flag: -1.23
```

## 参考:
[http://www.cplusplus.com/reference/ios/left/](http://www.cplusplus.com/reference/ios/left/)