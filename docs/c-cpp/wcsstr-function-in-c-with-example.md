# wcsstr()函数在 C++ 中用示例

> 原文:[https://www . geesforgeks . org/wcsstr-function-in-c-with-example/](https://www.geeksforgeeks.org/wcsstr-function-in-c-with-example/)

**wcsstr()** 函数在**cwcchar . h**头文件中定义。wcsstr()函数查找目标字符串中第一次出现的源。

**语法:**

```cpp
wchar_t* wcsstr(const wchar_t* dest, const wchar_t* src);
```

**参数:**该方法接受以下参数:

*   **src:** 它表示指向要搜索的空终止宽字符串的指针。
*   **dest:** 它表示指向我们必须搜索的空终止宽字符串的指针。

**返回值:**该方法的返回值取决于:

*   如果未找到 src，则返回空值
*   如果 src 指向空字符串，则返回目标
*   如果找到 src，wcsstr()函数将指针返回到目标中 src 的第一个宽字符。

下面的程序说明了上面的功能:

**例 1:** 找不到源时，返回 null

```cpp
// c++ program to demonstrate
// example of wcsstr() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize the destination string
    wchar_t dest[] = L"Geeks Are Geeks";

    // get the source string to be found
    wchar_t src[] = L"To";

    // Find the occurrence and print it
    wcout << wcsstr(dest, src);

    return 0;
}
```

**Output:**

**示例 2:** 当源为空时，返回目标字符串

```cpp
// c++ program to demonstrate
// example of wcsstr() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize the destination string
    wchar_t dest[] = L"Geeks Are Geeks";

    // get the source string to be found
    wchar_t src[] = L"";

    // Find the occurrence and print it
    wcout << wcsstr(dest, src);

    return 0;
}
```

**Output:**

```cpp
Geeks Are Geeks

```

**例 3:** 找到源后，返回源的目的地。

```cpp
// c++ program to demonstrate
// example of wcsstr() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize the destination string
    wchar_t dest[] = L"Geeks Are Geeks";

    // get the source string to be found
    wchar_t src[] = L"Are";

    // Find the occurrence and print it
    wcout << wcsstr(dest, L"Are");

    return 0;
}
```

**Output:**

```cpp
Are Geeks

```