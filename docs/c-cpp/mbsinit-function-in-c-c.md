# mbsinit()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/mbsinit-function-in-c-c/](https://www.geeksforgeeks.org/mbsinit-function-in-c-c/)

**mbsinit()** 是 C++ 中的一个内置函数，用于检查 *ps* (作为参数传递给该函数)是否指向描述初始转换状态的 mbstate_t 对象。对于任何表示初始状态的 mbstate_t 对象，或者如果 ps 是空指针，该函数返回非零值。
PS 指向的状态可以通过调用:
设置为初始状态

```cpp
// ps points now to a zero-valued object
memset (ps, 0, sizeof(*ps));
```

**语法:**

```cpp
int mbsinit( const mbstate_t* ps)
```

**参数:**该函数接受如下所述的一个参数:

*   **ps :** 指向 mbstate_t 对象的指针

**返回值:**该函数返回如下两个值:

*   如果 ps 不是空指针并且不代表初始转换状态，则为 0。
*   如果 ps 是空指针或表示初始转换状态，则非零。

以下程序说明了上述功能:
**程序 1 :**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// mbsinit() function

#include <bits/stdc++.h>
using namespace std;

// function to check if the object describes
// the initial conversion state
void checkfor(mbstate_t ps)
{
    // (mbstate_t) Type that holds the information necessary
    // to maintain the state when converting between
    // sequences of multibyte characters and
    // wide characters (either way).

    int func = mbsinit(&ps);

    if (func)
        cout<<"The conversion state is initial"
                                 <<" conversion state\n";

    else
        cout<<"The conversion state is not initial"
                                    <<" conversion state";
}

// Driver code
int main()
{
    setlocale(LC_ALL, "en_US.utf8");

    // initializing the string
    char str[] = "\u00df";

    // initial state
    mbstate_t ps = mbstate_t();

    // check if ps is liknked to
    // initial conversion state
    checkfor(ps);

    mbrlen(str, 1, &ps);

    // check if, after getting the
    // length of multibyte character
    checkfor(ps);

    return 0;
}
```

**Output:** 

```cpp
The conversion state is initial conversion state
The conversion state is not initial conversion state
```

**节目 2 :**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// mbsinit() function
// with empty string

#include <bits/stdc++.h>
using namespace std;

// function to check if
// object describes the initial conversion state
void checkfor(mbstate_t ps)
{
    // (mbstate_t) Type that holds the information necessary
    // to maintain the state when converting between
    // sequences of multibyte characters and
    // wide characters (either way).

    int func = mbsinit(&ps);

    if (func)
        cout << "the conversion state is initial"
                                <<" conversion state\n";

    else
        cout << "the conversion state is not initial"
                                <<" conversion state";
}

// Driver code
int main()
{
    setlocale(LC_ALL, "en_US.utf8");

    // initializing the string
    char str[] = "";

    // initial state
    mbstate_t ps = mbstate_t();

    // check if ps is liknked to
    // initial conversion state
    cout << "After ps is initialized, ";
    checkfor(ps);

    mbrlen(str, 0, &ps);

    // check if, after getting the
    // length of multibyte character
    cout << "After performing some task, ";
    checkfor(ps);

    return 0;
}
```

**Output:** 

```cpp
After ps is initialized, the conversion state is initial conversion state
After performing some task, the conversion state is initial conversion state
```