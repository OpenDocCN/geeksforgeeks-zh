# 是 C/C++

中的 iswupper()函数

> 原文:[https://www.geeksforgeeks.org/iswupper-function-in-c-c/](https://www.geeksforgeeks.org/iswupper-function-in-c-c/)

**iswupper()** 是 C/C++ 中的一个内置函数，它检查给定的宽字符**是否是大写字符**。在 CPP 头文件**<cwcytype . h>**中定义，该功能是 [isupper](https://www.geeksforgeeks.org/isupper-islower-application-c/) ( <cctype>)的宽字符等价物。</cctype>

**语法:**

```cpp
int iswupper(wint_t rs)
```

**参数:**该函数接受一个单一的强制参数 **rs** ，该参数指定要检查的宽字符。

**返回值:**函数返回两个值，如下所示:

*   **非零值**–如果 rs 有大写字符
*   **零**–如果 rs 没有大写字符

下面的程序说明了上述功能。
**节目一:**

```cpp
// C++ program to illustrate
// iswupper() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    wchar_t rs1 = 'S';
    wchar_t rs2 = 's';

    // Function to check if the character
    // is a uppercase character or not
    if (iswupper(rs1))
        wcout << rs1 << " is a uppercase character ";
    else
        wcout << rs1 << " is not a uppercase character ";
    wcout << endl;

    if (iswupper(rs2))
        wcout << rs2 << " is a uppercase character ";
    else
        wcout << rs2 << " is not a uppercase character ";

    return 0;
}
```

**Output:**

```cpp
S is a uppercase character 
s is not a uppercase character

```

**程序 2:**

```cpp
// C++ program to illustrate
// iswupper() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    wchar_t rs1 = 'R';
    wchar_t rs2 = '@';

    // Function to check if the character
    // is a uppercase character or not
    if (iswupper(rs1))
        wcout << rs1 << " is a uppercase character ";
    else
        wcout << rs1 << " is not a uppercase character ";
    wcout << endl;

    if (iswupper(rs2))
        wcout << rs2 << " is a uppercase character ";
    else
        wcout << rs2 << " is not a uppercase character ";

    return 0;
}
```

**Output:**

```cpp
R is a uppercase character 
@ is not a uppercase character

```