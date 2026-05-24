# iOS操纵器在C++中不显示point()函数

> 原文: [https://www.geeksforgeeks.org/ios-manipulators-noshowpoint-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-noshowpoint-function-in-c/)

C++中流操纵器的`noshowpoint()`方法用于清除指定字符串流的`showpoint`格式标志。只有当浮点值具有十进制值时，此标志才会以十进制显示浮点值。

## 语法

```cpp
ios_base& nosohowpoint (ios_base& str)
```

## 参数

该方法接受`ios_base`作为参数，该参数是要清除格式标志的流。

## 返回值

该方法返回设置了无显示点格式标志的`ios_base`流。

## 示例1

```cpp
// C++ code to demonstrate
// the working of noshowpoint() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the floating values
    double n1 = 10;
    double n2 = 20.0;

    cout.precision(5);

// Using noshowpoint()
    cout << "noshowpoint flag: "
         << noshowpoint
         << n1 << endl
         << n2 << endl;

    return 0;
}
```

**输出:**

```cpp
noshowpoint flag: 10
20
```

## 示例2

```cpp
// C++ code to demonstrate
// the working of noshowpoint() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the floating values
    double n3 = 30.1223;

    cout.precision(5);

// Using noshowpoint()
    cout << "noshowpoint flag: "
         << noshowpoint
         << n3 << endl;

    return 0;
}
```

**输出:**

```cpp
noshowpoint flag: 30.122
```

**参考:** [http://www.cplusplus.com/reference/ios/noshowpoint/](http://www.cplusplus.com/reference/ios/noshowpoint/)