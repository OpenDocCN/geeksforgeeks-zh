# C/c++ 中的 iswgraph()，示例

> 原文:[https://www . geeksforgeeks . org/isw graph-in-c-c-with-examples/](https://www.geeksforgeeks.org/iswgraph-in-c-c-with-examples/)

**iswgraph()** 是 C/C++ 中的一个内置函数，它检查给定的宽字符是否有图形表示。在 C++ 的**cwcytpe**头文件中定义。默认情况下，以下字符是图形:

*   **数字** (0 至 9)
*   **大写字母** (A 至 Z)
*   **小写字母** (a 至 z)
*   **标点符号**(！" #$% & '()*+，-。/:;？@[\]^_`{|}~)

**语法**:

```cpp
int iswgraph(ch)
```

**参数**:该函数接受单个强制参数 **ch** ，该参数指定了宽字符，我们必须检查它是否具有图形表示。

**返回值**:函数返回两个值，如下图所示。

*   如果 ch 具有图形表示字符，则返回非零值。
*   如果它不是图形表示字符，则返回 0。

下面的程序说明了上面的功能。

**程序 1** :

```cpp
// C++ program to illustrate
// iswgraph() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = '?';
    wchar_t ch2 = ' ';

    // Function to check if the character
    // has a graphical representation or not
    if (iswgraph(ch1))
        wcout << ch1 << " has graphical representation ";
    else
        wcout << ch1 << " does not have graphical representation ";
    wcout << endl;

    if (iswgraph(ch2))
        wcout << ch2 << " has graphical representation ";
    else
        wcout << ch2 << " does not have graphical representation ";

    return 0;
}
```

**Output:**

```cpp
? has graphical representation 
  does not have graphical representation

```

**程序 2** :

```cpp
// C++ program to illustrate
// iswgraph() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = ' ';
    wchar_t ch2 = '3';

    // Function to check if the character
    // has a graphical representation or not
    if (iswgraph(ch1))
        wcout << ch1 << " has graphical representation ";
    else
        wcout << ch1 << " does not have graphical representation ";
    wcout << endl;

    if (iswgraph(ch2))
        wcout << ch2 << " has graphical representation ";
    else
        wcout << ch2 << " does not have graphical representation ";

    return 0;
}
```

**Output:**

```cpp
does not have graphical representation 
3 has graphical representation

```