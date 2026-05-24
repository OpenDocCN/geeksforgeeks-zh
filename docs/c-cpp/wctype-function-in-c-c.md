# wctype()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wctype-function-in-c-c/](https://www.geeksforgeeks.org/wctype-function-in-c-c/)

**wctype()** 是 C/C++ 中的内置函数，它返回 wctype_t 类型的值，用于对宽字符进行分类。在 C++ 的**cwcytpe**头文件中定义。以下是可能的 wctype_t 类型:

| *字符串*的值 | 等效函数 |
| --- | --- |
| 空间 | isspace |
| 上面的 | 伊瑟普 |
| xdigit | iswxdigit |
| 打印 | 伊斯梅尔堡 |
| 泪点 | iswpoint |
| 图表 | 求根仪 |
| 降低 | islower |
| cntrl | 伊斯 wcntrl |
| 手指 | iswdigit |
| 希腊字母的第一个字母 | isalpha |
| 空白的 | isblank |
| alnum | 伊斯瓦尔纳姆 |

**语法:**

```cpp
wctype_t wctype(const char* str)
```

**参数:**该函数接受一个指定所需 wctype 类别的强制参数 *str* 。

**返回值:**函数返回两个值，如下所示:

*   该函数返回一个 wctype_t 对象，该对象可以与 iswctype()或 owctype()一起使用来检查宽字符的属性。
*   如果 *str* 没有提供当前 C 语言环境支持的类别，则返回零。

下面的程序说明了上面的功能。
**节目一:**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    wchar_t wc = L'@';

    // checks if the type is digit
    if (iswctype(wc, wctype("digit")))
        wcout << wc << L" is a digit";

    // checks if the type is alpha
    else if (iswctype(wc, wctype("alpha")))
        wcout << wc << L" is an alphabet";

    else
        wcout << wc << L" is neither an"
              << " alphabet nor a digit";

    return 0;
}
```

**Output:**

```cpp
@ is neither an alphabet nor a digit

```

**输出:**

```cpp
@ is neither an alphabet nor a digit
```

**程序 2:**

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    wchar_t wc = L'g';

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
g is an alphabet

```