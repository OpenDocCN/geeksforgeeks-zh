# towctrans()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/towctrans-function-in-c-c/](https://www.geeksforgeeks.org/towctrans-function-in-c-c/)

**towctrans()** 是 C/C++ 中的内置函数，它对由 *desc* 指定的宽字符 *wc* 进行转换。在 C/C++ 的*cwcytpe*头文件中定义。

**语法:**

```cpp
wint_t towctrans(wint_t wc, wctype_t desc)
```

**参数:**该函数接受两个强制参数，描述如下:

*   *WC*–需要转换的宽字符。
*   *desc*–从对 wctrans()的调用中获得的转换。

**返回值:**函数返回两个值，如下所示:

*   如果 *wc* 具有 desc 指定的属性，则它返回非零值。
*   如果它没有属性，则返回零。

下面的程序说明了上面的功能。

**程序 1:**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    wchar_t str[] = L"Switching Case";
    wcout << L"Before transformation" << endl;
    wcout << str << endl;

    for (int i = 0; i < wcslen(str); i++) {

        // checks if it is lowercase
        if (iswctype(str[i], wctype("lower")))

            // transform character to uppercase
            str[i] = towctrans(str[i], wctrans("toupper"));

        // checks if it is uppercase
        else if (iswctype(str[i], wctype("upper")))

            // transform character to uppercase
            str[i] = towctrans(str[i], wctrans("tolower"));
    }

    wcout << L"After transformation" << endl;

    // prints the transformed string
    wcout << str << endl;
    return 0;
}
```

**Output:**

```cpp
Before transformation
Switching Case
After transformation
sWITCHING cASE

```

**程序 2:**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    wchar_t str[] = L"gFg iS fUN";
    wcout << L"Before transformation" << endl;
    wcout << str << endl;

    for (int i = 0; i < wcslen(str); i++) {

        // checks if it is lowercase
        if (iswctype(str[i], wctype("lower")))
            // transform character to uppercase
            str[i] = towctrans(str[i], wctrans("toupper"));

        // checks if it is uppercase
        else if (iswctype(str[i], wctype("upper")))

            // transform character to lowercase
            str[i] = towctrans(str[i], wctrans("tolower"));
    }

    wcout << L"After transformation" << endl;

    // prints the transformed string
    wcout << str << endl;
    return 0;
}
```

**Output:**

```cpp
Before transformation
gFg iS fUN
After transformation
GfG Is Fun

```