# 清除 C/C++ 中的输入缓冲区

> 原文:[https://www . geesforgeks . org/clearing-the-input-buffer-in-cc/](https://www.geeksforgeeks.org/clearing-the-input-buffer-in-cc/)

**什么是缓冲？**
一个临时存储区被称为缓冲区。所有标准输入和输出设备都包含一个输入和输出缓冲器。在标准 C/C++ 中，流被缓冲，例如在标准输入的情况下，当我们按下键盘上的键时，它不会被发送到您的程序，而是被操作系统缓冲，直到时间被分配给该程序。

**对编程有什么影响？**
在各种情况下，可能需要清除不需要的缓冲区，以便在期望的容器中获得下一个输入，而不是在前一个变量的缓冲区中。例如，在遇到“scanf()”后的 C 的情况下，如果我们需要输入一个字符数组或字符，而在 C++ 的情况下，遇到“cin”语句后，我们需要输入一个字符数组或字符串，我们需要清除输入缓冲区，否则所需的输入被前一个变量的缓冲区占用，而不是被所需的容器占用。在第一次输入后，在输出屏幕上按下“回车”(回车)，因为前一个变量的缓冲区是新容器的空间(因为我们没有清除它)，程序跳过容器的后续输入。

**在**T2T4**C 编程**T7】的情况下

## C

```cpp
// C Code to explain why not
// clearing the input buffer
// causes undesired outputs
#include<stdio.h>
int main()
{
    char str[80], ch;

    // Scan input from user -
    // GeeksforGeeks for example
    scanf("%s", str);

    // Scan character from user-
    // 'a' for example
    ch = getchar();

    // Printing character array,
    // prints “GeeksforGeeks”)
    printf("%s\n", str);

    // This does not print
    // character 'a'
    printf("%c", ch);

    return 0;
}
```

输入:

```cpp
GeeksforGeeks
a
```

输出:

```cpp
GeeksforGeeks
```

**在** **的情况下** [的 **C++** 的](https://www.geeksforgeeks.org/c-plus-plus/)

## C++

```cpp
// C++ Code to explain why
// not clearing the input
// buffer causes undesired
// outputs
#include<iostream>
#include<vector>
using namespace std;

int main()
{
    int a;
    char ch[80];

    // Enter input from user
    // - 4 for example
    cin >> a;

    // Get input from user -
    // "GeeksforGeeks" for example
    cin.getline(ch,80);

    // Prints 4
    cout << a << endl;

    // Printing string : This does
    // not print string
    cout << ch << endl;

    return 0;
}
```

输入:

```cpp
4
GeeksforGeeks
```

输出:

```cpp
4
```

在上述两个代码中，输出没有按要求打印。原因是缓冲区被占用。“\n”字符将保留在缓冲区中，并作为下一个输入读取。

**怎么解决？**

**在**T2【C】的情况下:

**1。使用“while ((getchar())！= ' \ n ')；**:键入“while ((getchar())！= ' \ n ')；读取缓冲区字符直到结束，并丢弃它们(包括换行符)，并在“scanf()”语句清除输入缓冲区并允许在所需容器中输入后使用它。

## C

```cpp
// C Code to explain why adding
// "while ( (getchar()) != '\n');"
// after "scanf()" statement
// flushes the input buffer
#include<stdio.h>

int main()
{
    char str[80], ch;

    // scan input from user -
    // GeeksforGeeks for example
    scanf("%s", str);

    // flushes the standard input
    // (clears the input buffer)
    while ((getchar()) != '\n');

    // scan character from user -
    // 'a' for example
    ch = getchar();

    // Printing character array,
    // prints “GeeksforGeeks”)
    printf("%s\n", str);

    // Printing character a: It
    // will print 'a' this time
    printf("%c", ch);

    return 0;
}
```

输入:

```cpp
GeeksforGeeks
a
```

输出:

```cpp
GeeksforGeeks
a
```

**2。使用“fflush(stdin)”**:在“scanf()”语句后键入“fflush(stdin)”也将清除输入缓冲区，但避免使用它，根据 C++ 11 标准，它被称为输入流的“未定义”。

**在 C++ 的** **案例中:**

**1。使用“cin.ignore(numeric_limits::max()，' \ n ')；”** :-键入“cin.ignore(numeric_limits::max()，' \ n ')；”在“cin”语句之后，丢弃输入流中的所有内容，包括换行符。

## C++

```cpp
// C++ Code to explain how
// "cin.ignore(numeric_limits
// <streamsize>::max(),'\n');"
// discards the input buffer
#include<iostream>

// for <streamsize>
#include<ios>    

// for numeric_limits
#include<limits>
using namespace std;

int main()
{
    int a;
    char str[80];

    // Enter input from user
    // - 4 for example
    cin >> a;

    // discards the input buffer
    cin.ignore(numeric_limits<streamsize>::max(),'\n');

    // Get input from user -
    // GeeksforGeeks for example
    cin.getline(str, 80);

    // Prints 4
    cout << a << endl;

    // Printing string : This
    // will print string now
    cout << str << endl;

    return 0;
}
```

输入:

```cpp
4
GeeksforGeeks
```

输出:

```cpp
4
GeeksforGeeks
```

**2。使用“cin . sync()”:**在“CIN”语句后键入“cin.sync()”会丢弃缓冲区中剩余的所有内容。虽然“CIN . sync()”**在所有实现中都不起作用**(根据 C++ 11 和以上标准)。

## C++

```cpp
// C++ Code to explain how " cin.sync();"
// discards the input buffer
#include<iostream>
#include<ios>    
#include<limits>
using namespace std;

int main()
{
    int a;
    char str[80];

    // Enter input from user
    // - 4 for example
    cin >> a;

    // Discards the input buffer
    cin.sync();

    // Get input from user -
    // GeeksforGeeks for example
    cin.getline(str, 80);

    // Prints 4
    cout << a << endl;

    // Printing string - this
    // will print string now
    cout << str << endl;

    return 0;
}
```

输入:

```cpp
4
GeeksforGeeks
```

输出:

```cpp
4
```

**3。使用“cin>>ws”:**在“CIN”语句后键入“cin > > ws”会告诉编译器忽略缓冲区，并丢弃字符串或字符数组实际内容之前的所有空格。

## C++

```cpp
// C++ Code to explain how "cin >> ws"
// discards the input buffer along with
// initial white spaces of string

#include<iostream>
#include<vector>
using namespace std;

int main()
{
    int a;
    string s;

    // Enter input from user -
    // 4 for example
    cin >> a;

    // Discards the input buffer and
    // initial white spaces of string
    cin >> ws;

    // Get input from user -
    // GeeksforGeeks for example
    getline(cin, s);

    // Prints 4 and GeeksforGeeks :
    // will execute print a and s
    cout << a << endl;
    cout << s << endl;

    return 0;
}
```

输入:

```cpp
4
GeeksforGeeks
```

输出:

```cpp
4
GeeksforGeeks
```

本文由**曼吉特·辛格**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。