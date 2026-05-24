# iswblank()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/iswblank-function-in-c-c/](https://www.geeksforgeeks.org/iswblank-function-in-c-c/)

**isw blank()**是 C/C++ 中的一个内置函数，用于检查给定的宽字符是否为空白字符。在 C++ 的**cwcytpe**头文件中定义。

**语法**:

```cpp
int isblank(ch)
```

**参数**:该函数接受单个强制参数 ***ch*** ，指定宽字符，我们必须检查它是否为空字符。

**返回值**:该函数返回两个值，描述如下:

*   如果 ch 是空白字符，则返回非零值。
*   如果不是，则返回 0。

下面的程序说明了上述功能。

**程序 1** :

```cpp
// Program to illustrate
// isblank() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = ' ';
    wchar_t ch2 = 'i';

    // check if character is blank or not 
    if(isblank(ch1))
     cout << "ch1 is blank \n"; 
    else 
      cout << "ch1 is not blank\n";

    // check if character is blank or not 
     if(isblank(ch2))
     cout << "ch2 is blank \n"; 
    else 
     cout << "ch2 is not blank\n";

    return 0;
}
```

**Output:**

```cpp
ch1 is blank 
ch2 is not blank

```

**程序 2** :

```cpp
// Program to illustrate
// isblank() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = '3';
    wchar_t ch2 = ' ';

    // check if character is blank or not 
    if(isblank(ch1))
     cout << "ch1 is blank \n"; 
    else 
      cout << "ch1 is not blank\n";

    // check if character is blank or not 
     if(isblank(ch2))
     cout << "ch2 is blank \n"; 
    else 
     cout << "ch2 is not blank\n";

    return 0;
}
```

**Output:**

```cpp
ch1 is not blank
ch2 is blank

```