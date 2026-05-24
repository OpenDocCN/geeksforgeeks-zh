# wcstok()函数在 C++ 中用示例

> 原文:[https://www . geeksforgeeks . org/wcstok-function-in-c-with-example/](https://www.geeksforgeeks.org/wcstok-function-in-c-with-example/)

**wcstok()** 函数在**cwcchar . h**头文件中定义。wcstok()函数返回以 null 结尾的宽字符串中的下一个标记。指针 delim 指向分隔符，即分隔符。

。
**语法:**

```cpp
wchar_t* wcstok(wchar_t* str, 
                     const wchar_t* delim, 
                     wchar_t ** ptr);
```

**参数:**该方法取以下参数:

*   **字符串:**它表示指向要标记的空终止宽字符串的指针。
*   **delim:** 表示指向包含分隔符的空终止宽字符串的指针。
*   **ptr:** 它表示 wchar_t*类型的对象的指针，wcstok 使用它来存储其内部状态。

**返回值:**wcstok()函数返回指向下一个标记(如果有)开头的指针。否则返回零。
下面的程序举例说明上面的功能:
**例 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// c++ program to demonstrate
// example of wcstok() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Get the string
    wchar_t str[] = L"A computer science portal for geeks";

    // Creating the parameters of wcstok() method

    // Create the pointer of which
    // the next token is required
    wchar_t* ptr;

    // Define the delimiter of the string
    wchar_t delim[] = L" ";

    // Call the wcstok() method
    wchar_t* token = wcstok(str, delim, &ptr);

    // Print all tokens with the help of it
    while (token) {
        wcout << token << endl;
        token = wcstok(NULL, delim, &ptr);
    }

    return 0;
}
```

**Output:** 

```cpp
A
computer
science
portal
for
geeks
```