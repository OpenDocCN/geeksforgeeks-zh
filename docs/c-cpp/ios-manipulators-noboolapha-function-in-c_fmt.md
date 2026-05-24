# ios 操纵器 noboolalpha()函数在 C++ 中

> 原文：[https://www.geeksforgeeks.org/ios-manipulators-noboolalpha-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-noboolalpha-function-in-c/)

C++ 中流操纵器的 `noboolalpha()` 方法用于获取指定字符串流的 boolalpha 格式标志的整数值。

**语法：**

```cpp
ios_base& noboolalpha (ios_base& str)
```

**参数：** 该方法接受 `ios_base& str` 作为参数，该参数是为其提取格式标志的流。

**返回值：** 该方法返回带有 `noboolalpha` 格式标志的流 `str`。

**例 1：**

```cpp
// C++ code to demonstrate
// the working of noboolalpha() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the boolean flag
    bool flag = true;

// Using noboolalpha()
    cout << "noboolalpha flag: "
         << noboolalpha << flag << endl;

return 0;
}
```

**输出：**

```cpp
noboolalpha flag: 1
```

**例 2：**

```cpp
// C++ code to demonstrate
// the working of noboolalpha() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the boolean flag
    bool flag = false;

// Using noboolalpha()
    cout << "noboolalpha flag: "
         << noboolalpha << flag << endl;

return 0;
}
```

**输出：**

```cpp
noboolalpha flag: 0
```

**参考：** [http://www.cplusplus.com/reference/ios/noboolalpha/](http://www.cplusplus.com/reference/ios/noboolalpha/)