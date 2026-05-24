# 如何将 C 风格字符串转换为 std::string，反之亦然？

> 原文:[https://www . geesforgeks . org/how-convert-c-style-string-to-stdstring-反之亦然/](https://www.geeksforgeeks.org/how-to-convert-c-style-strings-to-stdstring-and-vice-versa/)

**什么是 [C 风格琴弦](https://www.geeksforgeeks.org/storage-for-strings-in-c/)？**
这些字符串是以空字符结束的字符数组。c 风格字符串可以通过以下方式声明:

**声明和初始化**

```cpp
/* To demonstrate C style strings */
#include<iostream>
using namespace std;
int main()
{
    /* Null character has to be added explicitly */
    char str1[8] = {'H' , 'E' , 'L' , 'L' , 'O' ,
                     '-','1','\0' };

    /* Compiler implicitly adds Null character */
    char str2[] = "HELLO-2" ;  

    /* Compiler implicitly adds Null character. 
       Note that string literals are typically stored
       as read only */
    const char *str3 = "HELLO-3" ;

    cout << str1 << endl << str2 << endl << str3;
    return 0;
} 
```

输出:

```cpp
HELLO-1
HELLO-2
HELLO-3

```

操作 c 风格的字符串有非常有用的功能，如 **strcpy()** 、 **strlen()** 、 **strpbrk()** 、 **strcat()** 、**strtr()**等等！(这些功能都是“ **cstring** ”表头的成员功能)。

**什么是 std::string？**
C++ 标准库包含函数和类。String 是它的一个类。这里我们处理一个字符串类的对象。这个 std::string 会自己处理并管理自己的内存。

**声明和初始化**

```cpp
/* To demonstrate std::string */
#include<iostream>
#include<string>           

using namespace std;
int main()
{
    /* s becomes object of class string. */
    string s;  

    /* Initializing with a value. */           
    s = "HELLO";

    /* Printing the value */          
    cout << s; 

    return 0;
}
```

输出:

```cpp
HELLO

```

**将 C 字符串转换为标准::字符串。**
但是我们为什么需要这种转型呢？从 C 字符串到 std::字符串？这是因为

*   Std::string 管理自己的空间。所以程序员不需要担心内存，不像 C 字符串(因为它们是字符数组)
*   它们易于操作。用于连接的“+”运算符，用于赋值的“=”运算符，可以使用常规运算符进行比较。
*   **string::find()** 和许多其他函数可以在 std::string 上实现，而不是在 C-Strings 上实现，因此这变得很方便。
*   迭代器可以用在 std::string 中，不能用在 C-string 中。

还有更多！这是它的代码:-

```cpp
/* To demonstrate C style string to std::string */
#include<bits/stdc++.h>

using namespace std;
int main()
{
    /*Initializing a C-String */
    const char *a = "Testing"; 
    cout << "This is a C-String : "<< a << endl;

    /* This is how std::string s is assigned
       though a  C string ‘a’ */
    string s(a);  

    /* Now s is a std::string and a is a C-String */
    cout << "This is a std::string : "<< s << endl;
    return 0;
}
```

输出:

```cpp
This is a C-String : Testing
This is a std::string : Testing

```

上述转换也适用于字符数组。

```cpp
        // Character array to std::string conversion 
	char a[] = "Testing"; 
	string s(a); 
```

**将 std::string 转换为 C 风格字符串**
为什么我们需要这个转换？从 std::字符串到 C 字符串？

*   正是因为 header 中有几个强大的功能，让我们的工作变得非常容易。
*   **atoi()** 、 **itoa()** ，还有更多函数只对 C 字符串起作用。

你也可以想到其他原因！
以下是转换代码:-

```cpp
/* To demonstrate std::string to  C style string */
#include<iostream>
#include<string> /* This header contains string class */
using namespace std;
int main()
{
    /* std::string initialized */
    string s = "Testing";  
    cout << "This is a std::string : "<< s << endl;

    /* Address of first character of std::string is 
       stored to char pointer a */
    char *a = &(s[0]); 

    /* Now 'a' has address of starting character
      of string */
    printf("%s\n", a);                 
    return 0;
}
```

输出:

```cpp
This is a std::string : Testing
This is a C-String : Testing

```

std::string 还有一个函数 **c_str()** ，可以用来获取空终止字符数组。

```cpp
/* To demonstrate std::string to C style string using
   c_str() */
#include<bits/stdc++.h>
using namespace std;

int main()
{
    /* std::string initialized */
    string s = "Testing";  
    cout << "This is a std::string : "<< s << endl;

    // c_str returns null terminated array of characters
    const char *a = s.c_str();

    /* Now 'a' has address of starting character
      of string */
    printf("%s\n", a);                 
    return 0;
}
```

输出:

```cpp
This is a std::string : Testing
This is a C-String : Testing

```

C 字符串和 std::字符串都有各自的优势。一个人应该懂得它们之间的转换，才能轻松有效地解决问题。
 **相关文章:**
[C++ 字符串类及其应用|集合 1](https://www.geeksforgeeks.org/c-string-class-and-its-applications/)
[C++ 字符串类及其应用|集合 2](https://www.geeksforgeeks.org/c-string-class-applications-set-2/)

本文由 **Nishant** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。