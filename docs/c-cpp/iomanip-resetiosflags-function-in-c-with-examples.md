# iomanip resetiosflags()函数在 C++ 中的应用示例

> 原文:[https://www . geeksforgeeks . org/iomanip-resetiosflags-function-in-c-with-examples/](https://www.geeksforgeeks.org/iomanip-resetiosflags-function-in-c-with-examples/)

C++ 中 **iomanip 库**的 **resetiosflags()** 方法用于将指定为该方法参数的 ios 库格式标志复位。
**语法:**

```cpp
resetiosflags (ios_base::format_flag)
```

**参数:**该方法接受 **format_flag** 作为参数，该参数是该方法要重置的 ios 库格式标志。
**返回值:**这个方法不返回任何东西。它只充当流操纵器。
**例 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate
// the working of resetiosflags() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    cout << "Before reset: \n"
         << hex
         << setiosflags(ios::showbase)
         << num << endl;

    // Using resetiosflags()
    cout << "Resetting showbase flag"
         << " using resetiosflags: \n"
         << resetiosflags(ios::showbase)
         << num << endl;

    return 0;
}
```

**Output:** 

```cpp
Before reset: 
0x32
Resetting showbase flag using resetiosflags: 
32
```

**例 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate
// the working of resetiosflags() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the integer
    int num = 50;

    cout << "Before reset: \n"
         << hex
         << setiosflags(ios::showbase)
         << num << endl;

    // Using resetiosflags()
    cout << "Resetting showbase and uppercase"
         << " flag using resetiosflags: \n"
         << resetiosflags(ios::showbase)
         << num << endl;

    return 0;
}
```

**Output:** 

```cpp
Before reset: 
0x32
Resetting showbase and uppercase flag using resetiosflags: 
32
```

**参考:**T2http://www.cplusplus.com/reference/iomanip/resetiosflags/