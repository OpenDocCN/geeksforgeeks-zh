# 是 C/C++

中的 iswctype()函数

> 原文:[https://www.geeksforgeeks.org/iswctype-function-in-c-c/](https://www.geeksforgeeks.org/iswctype-function-in-c-c/)

**iswcytype()**是 C/C++ 中的一个内置函数，它检查给定的宽字符是否具有某种属性。在 C/C++ 的**cwcytpe**头文件中定义

**语法:**

```cpp
int iswctype(wint_t wc, wctype_t desc)
```

**参数:**该函数接受两个强制参数，描述如下:

*   *WC*–要检查的宽字符。
*   *desc*–要测试的属性是从对 wctype()的调用中获得的。

**返回值:**函数返回两个值，如下所示:

*   如果 *wc* 具有 *desc* 指定的属性，则返回非零值。
*   否则返回零。

下面的程序说明了上面的功能。

**程序 1:**

```cpp
// Program to illustrate
// iswctype() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    wchar_t wc = L'A';

    // checks if the type is digit
    if (iswctype(wc, wctype("digit")))
        wcout << wc << L" is a digit";

    // checks if the type is alpha
    else if (iswctype(wc, wctype("alpha")))
        wcout << wc << L" is an alphabet";

    else
        wcout << wc << L" is neither "
              << "an alphabet nor a digit";

    return 0;
}
```

**Output:**

```cpp
A is an alphabet

```

**程序 2:**

```cpp
// Program to illustrate
// iswctype() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    wchar_t wc = L'5';

    // checks if the type is digit
    if (iswctype(wc, wctype("digit")))
        wcout << wc << L" is a digit";

    // checks if the type is alpha
    else if (iswctype(wc, wctype("alpha")))
        wcout << wc << L" is an alphabet";

    else
        wcout << wc << L" is neither"
              << " an alphabet nor a digit";

    return 0;
}
```

**Output:**

```cpp
5 is a digit

```