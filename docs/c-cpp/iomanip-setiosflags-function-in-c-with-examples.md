# iomanip setiosflags()函数在 C++ 中的使用示例

> 原文:[https://www . geesforgeks . org/iomanip-setios flags-function-in-c-with-examples/](https://www.geeksforgeeks.org/iomanip-setiosflags-function-in-c-with-examples/)

C++ 中 **iomanip 库**的 setiosflags **()** 方法用于设置指定为该方法参数的 ios 库格式标志。
**语法:**

```cpp
setiosflags (ios_base::format_flag)
```

**参数:**该方法接受 **format_flag** 作为参数，该参数是该方法要设置的 ios 库格式标志。
**返回值:**这个方法不返回任何东西。它只充当流操纵器。
**例 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate
// the working of setiosflags() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    // Using setiosflags()
    cout << "Setting showbase flag "
         << "using setiosflags: \n"
         << hex
         << setiosflags(ios::showbase)
         << num << endl;

    return 0;
}
```

**Output:** 

```cpp
Setting showbase flag using setiosflags: 
0x32
```

**例 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate
// the working of setiosflags() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    // Using setiosflags()
    cout << "Setting showbase and uppercase"
         << " flag using setiosflags: \n"
         << hex
         << setiosflags(
                ios::showbase
                | ios::uppercase)
         << num << endl;

    return 0;
}
```

**Output:** 

```cpp
Setting showbase and uppercase flag using setiosflags: 
0X32
```

**参考:**T2http://www.cplusplus.com/reference/iomanip/setiosflags/