# C/c++ 中的 wmemset()，示例

> 原文:[https://www.geeksforgeeks.org/wmemset-in-c-c-with-examples/](https://www.geeksforgeeks.org/wmemset-in-c-c-with-examples/)

**wmemset()** 函数是 C/C++ 中的一个内置函数，它将一个宽字符复制指定的次数到一个宽字符数组中。它在 C++ 中的**cwcchar**头文件中定义。

**语法**:

```cpp
wmemset(des, ch, count)
```

**参数**:该功能接受三个参数，描述如下。

*   **des** :指定复制宽字符到宽字符数组。
*   **ch** :指定要复制的宽字符。
*   **计数**:指定复制的次数。

**返回值**:该函数返回如下三个值:

*   如果**计数**大于 0，则函数返回 **des** 。
*   如果**计数**小于 0，可能会出现**分段故障**。
*   如果**计数**等于零，则该函数不做任何事情。

下面的程序说明了上述功能。
**节目 1** :

```cpp
// C++ program to illustrate the
// wmemset() function when count is greater than 0
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{
    wchar_t ch = L'G';
    wchar_t des[20];
    int count = 10;

    wmemset(des, ch, count);
    wcout << L"After copying " << ch << L" 10 times" << endl;

    for (int i = 0; i < count; i++)
        putwchar(des[i]);

    return 0;
}
```

**Output:**

```cpp
After copying G 10 times
GGGGGGGGGG

```

**程序 2** :

```cpp
// C++ program to illustrate the
// wmemset() function when count is 0
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{
    wchar_t ch = L'r';
    wchar_t des[20];
    int count = 0;

    wmemset(des, ch, count);
    wcout << L"After copying " << ch << L" 0 times" << endl;

    for (int i = 0; i < count; i++)
        putwchar(des[i]);

    return 0;
}
```

**Output:**

```cpp
After copying r 0 times

```

**Program 3**:

```cpp
// C++ program to illustrate the
// wmemset() function when 
// count is less than 0
// returns a segmentation fault 
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{
    wchar_t ch = L'q';
    wchar_t des[20];
    int count = -4;

    wmemset(des, ch, count);
    wcout << L"After copying " << ch << L" -4 times" << endl;

    for (int i = 0; i < count; i++)
        putwchar(des[i]);

    return 0;
}
```

**输出:**

```cpp
Runtime Errors:
Segmentation Fault (SIGSEGV)

```