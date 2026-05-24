# iswcntrl()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/iswcntrl-function-in-c-c/](https://www.geeksforgeeks.org/iswcntrl-function-in-c-c/)

**iswcntrl()** 是 C++ STL 中的一个内置函数，它检查给定的宽字符是否是控制字符。在 C/C++ 的**cwcytpe**头文件中定义。

**语法:**

```cpp
int iswcntrl(wint_t ch)
```

**参数:**该函数接受单个强制参数 *ch* ，该参数指定了我们必须检查是否为控制字符的宽字符。

**返回值:**函数返回两个值，如下所示:

*   如果 *ch* 是控制字符，则返回非零值。
*   如果不是，则返回 0。

下面的程序说明了上面的功能。
**节目一:**

```cpp
// C++ program to illustrate the
// iswcntrl() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    wchar_t ch1 = L'\n';

    // checks if it is a control character
    if (iswcntrl(ch1))
        wcout << "It is a control Character";

    else
        wcout << "It is not a control Character";
    return 0;
}
```

**Output:**

```cpp
It is a control Character

```

**程序 2:**

```cpp
// C++ program to illustrate the
// iswcntrl() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    wchar_t ch1 = L'@';

    // checks if it is a control character
    if (iswcntrl(ch1))
        wcout << "It is a control Character";

    else
        wcout << "It is not a control Character";

    return 0;
}
```

**Output:**

```cpp
It is not a control Character

```