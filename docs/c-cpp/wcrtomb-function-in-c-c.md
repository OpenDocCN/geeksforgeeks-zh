# wcrtomb()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wcrtomb-function-in-c-c/](https://www.geeksforgeeks.org/wcrtomb-function-in-c-c/)

C/C++ 中的 **wcrtomb()** 函数将宽字符转换为窄多字节表示。宽字符 **wc** 被翻译成它的多字节等价物，并存储在由 **s** 指向的数组中。该函数返回由 **s** 指向的等效多字节序列的字节长度。

**语法:**

```cpp
size_t wcrtomb( char* s, wchar_t wc, mbstate_t* ps )
```

**参数:**该功能接受三个强制参数，描述如下:

*   **s:** 指定指向一个数组的指针，该数组足够大以容纳一个多字节序列
*   **wc:** 指定要转换的宽字符。
*   **ps:** 指定解释多字节字符串时使用的转换状态的指针

**返回值:**该函数返回如下两个值:

*   成功后，它返回写入字符数组的字节数，字符数组的第一个元素由 s 指向。
*   否则返回-1，errno 设置为 **EILSEQ** 。

以下程序说明了上述功能:
**程序 1:**

```cpp
// C++ program to illustrate the
// wcrtomb() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    setlocale(LC_ALL, "en_US.utf8");

    // initialize the string
    wchar_t wc[] = L"z\u00df\u6c34\U0001f34c";

    // array large enough to hold a multibyte sequence
    char s[25];
    int returnV;

    // initial state
    mbstate_t ps = mbstate_t();
    for (int i = 0; i < wcslen(wc); i++) {
        returnV = wcrtomb(s, wc[i], &ps);

        // print byte size, if its a valid character
        if (returnV != -1)
            cout << "Size of " << s << " is "
                 << returnV << " bytes" << endl;
        else
            cout << "Invalid wide character" << endl;
    }

    return 0;
}
```

**Output:**

```cpp
Size of z is 1 bytes
Size of Ã? is 2 bytes
Size of æ°´ is 3 bytes
Size of ð?? is 4 bytes

```

**程序 2 :**

```cpp
// C++ program to illustrate the
// wcrtomb() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    setlocale(LC_ALL, "en_US.utf8");

    // initialize the string
    wchar_t wc[] = L"u\u00c6\u00f5\u01b5";

    // array large enough to hold a multibyte sequence
    char s[20];
    int returnV;

    // initial state
    mbstate_t ps = mbstate_t();
    for (int i = 0; i < wcslen(wc); i++) {
        returnV = wcrtomb(s, wc[i], &ps);

        // print byte size, if its a valid character
        if (returnV != -1)
            cout << "Size of " << s << " is "
                 << returnV << " bytes" << endl;
        else
            cout << "Invalid wide character" << endl;
    }

    return 0;
}
```

**Output:**

```cpp
Size of u    Ì_e is 1 bytes
Size of Ã?Ì_e is 2 bytes
Size of ÃµÌ_e is 2 bytes
Size of ÆµÌ_e is 2 bytes

```