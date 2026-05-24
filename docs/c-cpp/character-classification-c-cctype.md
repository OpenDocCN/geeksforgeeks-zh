# c++ 中的字符分类:cctype

> 原文:[https://www . geesforgeks . org/character-classification-c-cctype/](https://www.geeksforgeeks.org/character-classification-c-cctype/)

使用函数库**中指定的函数，C++ 中的字符分类是可能的。本文讨论了字符分类的众多功能。** 

****1。isalpha() :** 如果字符是字母表则此函数返回 **true，否则返回 false。 **a-z 和 A-Z** 中的所有字符根据该功能返回真。****

****2。isalnum() :** 如果字符是字母或数字则此函数返回 **true，否则返回 false。 **a-z、a-z 的所有字符和**的所有数字根据此功能返回真。****

****3。isdigit() :** 如果字符是数字则此函数返回 **true，否则返回 false。所有**所有数字**按此功能返回真。****

```cpp
// C++ program to demonstrate insalpha(), isnum() 
// and isdigit()
#include <cctype>
#include <iostream>
using namespace std;

int main()
{
    // initializing character array
    char ch[5] = "g1";

    // checking for isalpha() function
    for (int i=0; i<2; i++)
    {
        if (isalpha(ch[i]))
            cout << ch[i] << " is alphabet" << endl;
        else
            cout << ch[i] << " is not alphabet" << endl;
    }

    cout << endl;

    // checking for isalnum() function
    for (int i=0; i<2; i++)
    {
        if (isalnum(ch[i]))
            cout << ch[i] << " is alphanumeric" << endl;
        else
            cout << ch[i]  << " is not alphanumeric" << endl;
    }

    cout << endl;

    // checking for isdigit() function
    for (int i=0; i<2; i++)
    {
        if (isdigit(ch[i]))
            cout << ch[i]  <<  " is digit" << endl;
        else
            cout << ch[i] << " is not digit" << endl;
    }
}
```

**输出:**

```cpp
g is alphabet
1 is not alphabet

g is alphanumeric
1 is alphanumeric

g is not digit
1 is digit 
```

****4。isblank() :** 如果字符是空格或制表符则该函数返回 **true，否则返回 false。****

****5。isspace() :** 如果字符是空格、制表符或空白控制码(例如，\n，\r ) 则该函数返回 **true，否则返回 false。****

****6。iscentrl():**如果字符是 tab 或任何控制代码则此函数返回 **true，否则返回 false。****

```cpp
// C++ program to demonstrate iscntrl(), isblank() and
// isspace()
#include <cctype>
#include <iostream>
using namespace std;

int main()
{
    // initializing character array
    char ch[4] = " \n\t";

    // checking for iscntrl() function
    for (int i=0; i<3; i++)
    {
        if (iscntrl(ch[i]))
            cout << " Character is control code " << endl;
        else
            cout << " Character is not control code" << endl;
    }

    cout << endl;

    // checking for isblank() function
    for (int i=0; i<3; i++)
    {
        if (isblank(ch[i]))
            cout << " Character is blank" << endl;
        else
            cout << " Character is not blank" << endl;
    }

    cout << endl;

    // checking for isspace() function
    for (int i=0; i<3; i++)
    {
        if (isspace(ch[i]))
            cout << " Character is space" << endl;
        else
            cout << " Character is not space" << endl;
    }
}
```

**输出:**

```cpp
 Character is not control code
 Character is control code 
 Character is control code 

 Character is blank
 Character is not blank
 Character is blank

 Character is space
 Character is space
 Character is space 
```

****7。isprint() :** 如果字符可在控制台上打印，即除控制代码以外的所有字符，则该函数返回 **true，否则返回 false。****

****8。isxdigit() :** 如果字符是十六进制的，即 0-9 和 a-f ，则此函数返回 **true，否则返回 false。****

****9。ispunt():**如果字符是标点符号则此函数返回 **true，否则返回 false。****

```cpp
// C++ program to demonstrate isprint(), isxdigit() and
// ispunct()
#include <cctype>
#include <iostream>
using namespace std;

int main()
{
    // initializing character array
    char ch[6] = "\t@gf1";

    // checking for isprint() function
    for (int i=0; i<5; i++)
    {
        if (isprint(ch[i]))
            cout << ch[i] << " is printable character " << endl;
        else
            cout << ch[i] << " is not printable Character" << endl;
    }

    cout << endl;

    // checking for isxdigit() function
    for (int i=0; i<5; i++)
    {
        if (isxdigit(ch[i]))
            cout << ch[i] << " is hexadecimal Character" << endl;
        else
            cout << ch[i] << " is not hexadecimal Character" << endl;
    }

    cout << endl;

    // checking for ispunct() function
    for (int i=0; i<5; i++)
    {
        if (ispunct(ch[i]))
            cout << ch[i] << "  is punctuation mark" << endl;
        else
            cout << ch[i] <<  "  is not punctuation mark" << endl;
    }
}
```

**输出:**

```cpp
 is not printable Character
@ is printable character 
g is printable character 
f is printable character 
1 is printable character 

	 is not hexadecimal Character
@ is not hexadecimal Character
g is not hexadecimal Character
f is hexadecimal Character
1 is hexadecimal Character

	  is not punctuation mark
@  is punctuation mark
g  is not punctuation mark
f  is not punctuation mark
1  is not punctuation mark 
```

**参考:[http://www.cplusplus.com/reference/cctype/](http://www.cplusplus.com/reference/cctype/)T2】**

**本文由 **[曼吉特·辛格(S.Nandini)](https://www.facebook.com/manjeet.04.singh)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**