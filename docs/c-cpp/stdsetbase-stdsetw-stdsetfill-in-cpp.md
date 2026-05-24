# std::setbase，std::setw，std::setfill 在 C++ 中

> 原文:[https://www . geesforgeks . org/stdsetbase-stdsetw-stdsetfill-in-CPP/](https://www.geeksforgeeks.org/stdsetbase-stdsetw-stdsetfill-in-cpp/)

有用的输入/输出操纵器是**标准::设置基**、**标准::设置**和**标准::设置填充**。这些在中定义，是非常有用的函数。

*   **std::base** :设置 basefield 标志；将基字段设置为其可能的值之一:dec、hex 或 oct。
    **句法**:

```cpp
std::setbase (int base);
decimal : if base is 10
hexadecimal : if base is 16
octal : if base is 8
zero : if base is any other value.
```

*   **实现:**该代码使用 std::setbase 操纵器将十六进制设置为基字段选择标志。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP Program to illustrate
// std::setbase manipulator
#include <iostream>
#include <iomanip> // std::setbase

int main()
{
    // set base to hexadecimal
    std::cout << std::setbase(16);

    // displaying 255 in hexadecimal
    std::cout << 255 << std::endl;

    // set base to Octal
    std::cout << std::setbase(8);

    // displaying 255 in Octal
    std::cout << 255 << std::endl;
    return 0;
}
```

*   **输出:**

```cpp
ff
377
```

*   **std::setw** :设置字段宽度；设置用于输出操作的字段宽度。就像在作为操纵器插入/提取成员宽度的流上用 n 作为参数调用成员宽度一样(它可以在输入流或输出流上插入/提取)。
    **句法**:

```cpp
std::setw (int n);
where n is Number of characters to 
be used as field width.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP Program to illustrate
// std::setw manipulator
#include <iostream>
#include <iomanip> // std::setw

int main()
{

    // set width of 10
    std::cout << std::setw(10);
    std::cout << 100 << std::endl;

    std::string str = "GFG";

    // set width of 12
    std::cout << std::setw(12);

    std::cout << str << std::endl;
    return 0;
}
```

*   **输出:**

```cpp
       100
         GFG
```

*   **注意:**这里给 setw()的参数是输出的最小宽度，所以如果我们的输出宽度大于参数的值，那么输出宽度将不是给 setw()的参数，而是等于输出大小(即输出不会被截断)。*setw()的默认宽度为 0。*
    **例:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include<iomanip>
#include<string>
using std::cout;
using std::string;
using std::endl;

int main() {
    string temp="Hello setw";
    cout<<std::setw(5)<<temp<<endl;
    return 0;
}
```

*   **输出:**

```cpp
Hello setw
```

*   **std::setfill** :设置填充字符；将 c 设置为流的填充字符。就像在作为操纵器插入的流上用 c 作为参数调用成员填充一样(可以在输出流上插入)。
    **句法**:

```cpp
std::setfill (char_type c);
char_type is the type of characters 
used by the stream (i.e., its first class template 
parameter, charT).
```

*   **实施**:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP Program to test std::setfill manipulator
#include <iostream>
#include <iomanip> // std::setfill, std::setw

int main()
{
    // setfill is x and width is set as 10
    std::cout << std::setfill('x') << std::setw(10);

    std::cout << 77 << std::endl;

    std::string str = "Geeks";

    // setfill is G and width is set as 10
    // And std::left is used set str to left side
    std::cout << std::left << std::setfill('G') << std::setw(10);

    std::cout << str << std::endl;
    return 0;
}
```

*   输出:

```cpp
xxxxxxxx77
GeeksGGGGG
```

**模式使用标准:设置和标准:填充**；

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP Program to print
// pattern using std::setw and std::fill
#include <iostream>
#include <iomanip> // std::setfill, std::setw

int main()
{
    int n = 5;
    for (int i = 1; i <= n; i++) {
        std::cout << std::left << std::setfill(' ') << std::setw(n);
        std::cout << std::string(i, '*') << std::endl;
    }
}
```

**输出:**

```cpp
*
**
***
****
*****
```

本文由 [**舒巴姆拉纳**](https://auth.geeksforgeeks.org/profile.php?user=shubham_rana_77&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。