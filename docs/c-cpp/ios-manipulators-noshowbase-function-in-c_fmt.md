# ios操纵器noshowbase()函数在C++中

> 原文：`https://www.geeksforgeeks.org/ios-manipulators-noshowbase-function-in-c/`

C++中流操纵器的`noshowbase()`方法用于清除指定字符串流的`showbase`格式标志。此标志仅显示十进制的整数。

## 语法

```cpp
ios_base& noshowbase (ios_base& str)
```

## 参数

该方法接受`ios_base& str`作为参数，该参数是要清除格式标志的流。

## 返回值

该方法返回设置了`noshowbase`格式标志的流`str`。

## 例1

```cpp
// C++ code to demonstrate
// the working of noshowbase() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the integer
    int num = 50;

// Using noshowbase()
    cout << "noshowbase flag: "
         << oct
         << noshowbase
         << num << endl;

    return 0;
}
```

输出：

```cpp
noshowbase flag: 62
```

## 例2

```cpp
// C++ code to demonstrate
// the working of noshowbase() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the integer
    int num = 50;

// Using noshowbase()
    cout << "noshowbase flag: "
         << hex
         << noshowbase
         << num << endl;

    return 0;
}
```

输出：

```cpp
noshowbase flag: 32
```

## 参考

`http://www.cplusplus.com/reference/ios/noshowbase/`