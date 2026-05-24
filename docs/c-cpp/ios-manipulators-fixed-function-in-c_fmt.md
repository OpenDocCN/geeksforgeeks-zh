# C++ 中的 `fixed()` 流操纵器

> 原文：[https://www.geeksforgeeks.org/ios-manipulators-fixed-function-in-c/](https://www.geeksforgeeks.org/ios-manipulators-fixed-function-in-c/)

C++ 中的 `fixed()` 流操纵器方法用于设置指定字符串流的 `floatfield` 格式标志。此标志将 `floatfield` 设置为 `fixed`。这意味着浮点值将以定点表示法写入。

**语法：**

```cpp
ios_base& fixed (ios_base& str)
```

**参数：** 该方法接受 `ios_base& str` 作为参数，该参数是受格式标志影响的流。

**返回值：** 该方法返回设置了内部格式标志的 `ios_base& str` 流。

**例 1：**

```cpp
// C++ code to demonstrate
// the working of fixed() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the float values
    double x = 1.23;

cout.precision(5);

cout << "without fixed flag: "
         << x << endl;

// Using fixed()
    cout << "with fixed flag: "
         << fixed << x << endl;

return 0;
}
```

**输出：**

```cpp
without fixed flag: 1.23
with fixed flag: 1.23000
```

**例 2：**

```cpp
// C++ code to demonstrate
// the working of fixed() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the float values
    double x = 1.0;

cout.precision(5);

cout << "without fixed flag: "
         << x << endl;

// Using fixed()
    cout << "with fixed flag: "
         << fixed << x << endl;

return 0;
}
```

**输出：**

```cpp
without fixed flag: 1
with fixed flag: 1.00000
```

**例 3：**

```cpp
// C++ code to demonstrate
// the working of fixed() function

#include <iostream>

using namespace std;

int main()
{

// Initializing the float values
    double x = 1.23e9;

cout.precision(5);

cout << "without fixed flag: "
         << x << endl;

// Using fixed()
    cout << "with fixed flag: "
         << fixed << x << endl;

return 0;
}
```

**输出：**

```cpp
without fixed flag: 1.23e+09
with fixed flag: 1230000000.00000
```

**参考：** [http://www.cplusplus.com/reference/ios/fixed/](http://www.cplusplus.com/reference/ios/fixed/)