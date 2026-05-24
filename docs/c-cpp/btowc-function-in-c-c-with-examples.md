# btowc()函数在 C/C++ 中的应用举例

> 原文:[https://www . geesforgeks . org/btowc-function-in-c-c-with-examples/](https://www.geeksforgeeks.org/btowc-function-in-c-c-with-examples/)

**btowc()** 是 C/C++ 中的一个内置函数，它将一个字符转换为它的宽字符等价物。在 C++ 的**cwcchar**头文件中定义。

**语法**:

```cpp
wint_t btowc( int ch );
```

**参数**:该函数接受单个强制参数 **ch** ，该参数指定要转换为其宽字符的单字节字符。

**返回值** :
如果 ch 是有效的单字节字符，该函数返回 ch 的宽字符表示。如果 ch 是 **EOF** ，则返回 **WEOF** 。

下面的程序说明了上面的功能。

**程序 1** :

```cpp
// Program to illustrate
// btowc() function
#include <cstring>
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{
    char str[] = "Geeksfor\xf4\xdgeeks";
    wchar_t wc;
    int count = 0;

    for (int i = 0; i < strlen(str); i++) {

        wc = btowc(str[i]);
        if (wc != WEOF)
            count++ ;
    }

    cout << count << " out of " << strlen(str)
         << " Characters were successfully widened";
    return 0;
}
```

**Output:**

```cpp
14 out of 15 Characters were successfully widened

```

**程序 2** :

```cpp
// Program to illustrate
// btowc() function
#include <cstring>
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{
    char str[] = "Ishwar\xa1\xcGupta";
    wchar_t wc;
    int count = 0;

    for (int i = 0; i < strlen(str); i++) {

        wc = btowc(str[i]);
        if (wc != WEOF)
            count++ ;
    }

    cout << count << " out of " << strlen(str)
         << " Characters were successfully widened";
    return 0;
}
```

**Output:**

```cpp
12 out of 13 Characters were successfully widened

```