# C++ 字符串类及其应用

> 原文:[https://www . geesforgeks . org/c-string-class-and-its-applications/](https://www.geeksforgeeks.org/c-string-class-and-its-applications/)

在 C++ 中，我们可以通过以下两种方式之一来存储字符串

1.  [C 风格琴弦](https://www.geeksforgeeks.org/storage-for-strings-in-c/)
2.  字符串类(在这篇文章中讨论)

在这篇文章中，讨论了第二种方法。字符串类是 C++ 库的一部分，它支持比 C 风格字符串更多的功能。
C++ string 类内部使用 char 数组存储字符，但是所有的内存管理、分配和 null 终止都是由 string 类本身处理的，这就是为什么它易于使用的原因。C++ 字符串的长度可以在运行时更改，因为内存的动态分配类似于向量。由于 string 类是一个容器类，我们可以使用类似于其他容器(如 vector、set 和 map)的迭代器来迭代它的所有字符，但是通常，我们使用一个简单的 for 循环来迭代字符，并使用[]运算符对它们进行索引。
C++ 字符串类有很多函数可以轻松处理字符串。下面的代码演示了其中大部分有用的功能。

```cpp
// C++ program to demonstrate various function string class
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // various constructor of string class

    // initialization by raw string
    string str1("first string");

    // initialization by another string
    string str2(str1);

    // initialization by character with number of occurrence
    string str3(5, '#');

    // initialization by part of another string
    string str4(str1, 6, 6); //    from 6th index (second parameter)
                             // 6 characters (third parameter)

    // initialization by part of another string : iterator version
    string str5(str2.begin(), str2.begin() + 5);

    cout << str1 << endl;
    cout << str2 << endl;
    cout << str3 << endl;
    cout << str4 << endl;
    cout << str5 << endl;

    //  assignment operator
    string str6 = str4;

    // clear function deletes all character from string
    str4.clear();

    //  both size() and length() return length of string and
    //  they work as synonyms
    int len = str6.length(); // Same as "len = str6.size();"

    cout << "Length of string is : " << len << endl;

    // a particular character can be accessed using at /
    // [] operator
    char ch = str6.at(2); //  Same as "ch = str6[2];"

    cout << "third character of string is : " << ch << endl;

    //  front return first character and back returns last character
    //  of string

    char ch_f = str6.front();  // Same as "ch_f = str6[0];"
    char ch_b = str6.back();   // Same as below
                               // "ch_b = str6[str6.length() - 1];"

    cout << "First char is : " << ch_f << ", Last char is : "
         << ch_b << endl;

    // c_str returns null terminated char array version of string
    const char* charstr = str6.c_str();
    printf("%s\n", charstr);

    // append add the argument string at the end
    str6.append(" extension");
    //  same as str6 += " extension"

    // another version of append, which appends part of other
    // string
    str4.append(str6, 0, 6);  // at 0th position 6 character

    cout << str6 << endl;
    cout << str4 << endl;

    //  find returns index where pattern is found.
    //  If pattern is not there it returns predefined
    //  constant npos whose value is -1

    if (str6.find(str4) != string::npos)
        cout << "str4 found in str6 at " << str6.find(str4)
             << " pos" << endl;
    else
        cout << "str4 not found in str6" << endl;

    //  substr(a, b) function returns a substring of b length
    //  starting from index a
    cout << str6.substr(7, 3) << endl;

    //  if second argument is not passed, string till end is
    // taken as substring
    cout << str6.substr(7) << endl;

    //  erase(a, b) deletes b characters at index a
    str6.erase(7, 4);
    cout << str6 << endl;

    //  iterator version of erase
    str6.erase(str6.begin() + 5, str6.end() - 3);
    cout << str6 << endl;

    str6 = "This is a examples";

    //  replace(a, b, str)  replaces b characters from a index by str
    str6.replace(2, 7, "ese are test");

    cout << str6 << endl;

    return 0;
}
```

输出:

```cpp
first string
first string
#####
string
first
Length of string is : 6
third character of string is : r
First char is : s, Last char is : g
string
string extension
string
str4 found in str6 at 0 pos
ext
extension
string nsion
strinion
These are test examples
```

如上面的代码所示，我们可以通过 size()和 length()获得字符串的长度，但是 length()是字符串的首选。我们可以通过+=或 append()将一个字符串连接到另一个字符串，但是+=比 append()稍慢，因为每次调用+时都会产生一个新的字符串(创建新的缓冲区)，这在许多 append 操作的情况下会产生一点开销。

**应用程序:**
在上述字符串函数的基础上，一些应用程序编写如下:

```cpp
// C++ program to demonstrate uses of some string function
#include <bits/stdc++.h>
using namespace std;

// this function returns floating point part of a number-string
string returnFloatingPart(string str)
{
    int pos = str.find(".");
    if (pos == string::npos)
        return "";
    else
        return str.substr(pos + 1);
}

// This function checks whether a string contains all digit or not
bool containsOnlyDigit(string str)
{
    int l = str.length();
    for (int i = 0; i < l; i++)
    {
        if (str.at(i) < '0' || str.at(i) > '9')
            return false;
    }
    //  if we reach here all character are digits
    return true;
}

// this function replaces all single space by %20
// Used in URLS
string replaceBlankWith20(string str)
{
    string replaceby = "%20";
    int n = 0;

    // loop till all space are replaced
    while ((n = str.find(" ", n)) != string::npos )
    {
        str.replace(n, 1, replaceby);
        n += replaceby.length();
    }
    return str;
}

// driver function to check above methods
int main()
{
    string fnum = "23.342";
    cout << "Floating part is : " << returnFloatingPart(fnum) 
         << endl;

    string num = "3452";
    if (containsOnlyDigit(num))
        cout << "string contains only digit" << endl;

    string urlex = "google com in";
    cout << replaceBlankWith20(urlex) << endl;

    return 0;      
}
```

输出:

```cpp
Floating part is : 342
string contains only digit
google%20com%20in
```

**相关文章**:

*   [如何在 C++ 中快速反转一个字符串？](https://www.geeksforgeeks.org/quickly-reverse-string-c/)
*   [C++ 字符串类及其应用|集合 2](https://www.geeksforgeeks.org/c-string-class-applications-set-2/)
*   [c++ 中的字符串数组](https://www.geeksforgeeks.org/array-strings-c-3-different-ways-create/)
*   [在 C++ 中将字符串转换为数字，反之亦然](https://www.geeksforgeeks.org/converting-string-to-number-and-vice-versa-in-c/)

本文由乌卡什·特里维迪供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论