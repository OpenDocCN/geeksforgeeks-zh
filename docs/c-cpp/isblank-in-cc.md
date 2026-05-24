# 是 C/C++

中的 blank()

> 原文:[https://www.geeksforgeeks.org/isblank-in-cc/](https://www.geeksforgeeks.org/isblank-in-cc/)

如果 ch 是 isspace()返回 true 并用于分隔单词的字符，则 **isblank()** 函数返回非零值。因此，对于英语来说，空白字符是空格和水平制表符。

```cpp
Header File : 
ctype.h

Declaration : 
int isblank(int ch)

```

【isblank()和 isspace()
的区别如果字符是空格，则 **isspace()** 简单地返回 true。换句话说，空白字符是用于分隔一行文本中的单词的空格字符，isblank()用于标识它。

**isblank()** 将空白字符视为制表符(' \t ')和空格字符(' ')。
**isspace()** 考虑空格字符:(' ')–空格，(' \ t ')–水平制表符，(' \ n ')–换行符，(' \ v ')–垂直制表符，(' \ f ')–换行符，(' \ r ')–回车符

示例:

```cpp
Input:  Geeks for Geeks
Output: Geeks
        for 
        Geeks

```

说明:由于极客有两个空格，用下划线(_ ) :
极客为极客
我们用换行符代替空格。

**isblank() C++ 程序:**
这段代码逐字符打印出字符串，用换行符替换任何空白字符。

```cpp
// CPP program to demonstrate working
// of isblank()
#include <ctype.h>
#include <iostream>
using namespace std;

int main()
{
    string str = "Geeks for Geeks";
    int i = 0;

    // to store count of blanks
    int count = 0;
    while (str[i]) {

        // to get ith character
        // from string
        char ch = str[i++ ];

        // mark a new line when space
        // or horizontal tab is found
        if (isblank(ch)) {
            cout << endl;
            count++ ;
        }
        else
            cout << ch;
    }

       cout << "\nTotal blanks are : "
            << count << endl;
    return 0;
}
```

输出:

```cpp
Geeks
for
Geeks
Total blanks are : 2

```