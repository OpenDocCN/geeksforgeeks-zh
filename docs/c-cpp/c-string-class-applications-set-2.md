# C++ 字符串类及其应用|集合 2

> 原文:[https://www . geesforgeks . org/c-string-class-applications-set-2/](https://www.geeksforgeeks.org/c-string-class-applications-set-2/)

我们已经在下面的集合 1 中讨论了 String 类及其一些函数。

[C++ 字符串类及其应用|集合 1](https://www.geeksforgeeks.org/c-string-class-and-its-applications/)

本文将讨论更多的函数

**字符串 vs 字符数组**
在 C++ 中，除了字符数组之外，还有一种类似的实现字符串的方式，那就是使用字符串类，它是 C++ 标准库的一部分。要使用字符串类实现字符串，我们需要添加头文件**。字符数组和字符串的基本区别是，在字符数组的情况下，大小必须在声明时分配，即一旦分配，所有内存都是固定的，不能在运行时更改。而对于 string，在声明时不需要指定大小和分配固定内存。**

```cpp
// C++ program to demonstrate Character Array
// and String
#include<iostream>
#include<string>// for string class
using namespace std;
int main()
{
    // Size has to be predefined in character array
    char str[80] = "GeeksforGeeks";

    // Size not predefined in string
    string s("GeeksforGeeks");

    // Printing character array and string
    cout << str << endl;
    cout << s << endl;

    return 0;
}
```

**输出:**

```cpp
GeeksforGeeks
GeeksforGeeks 
```

****一些有用的字符串函数****

*   ****compare(string_to_compare )** :- It is used to compare two strings. It returns the difference of second string and first string in integer.

    ```cpp
    // C++ program to demonstrate use of compare()
    #include<iostream>
    #include<string>
    using namespace std;
    int main()
    {
        string str("GeeksforGeeks");
        string str1("GeeksforGeeks");

        // Comparing strings using compare()
        if ( str.compare(str1) == 0 )
            cout << "Strings are equal";
        else 
            cout << "Strings are unequal";
        return 0;
    }
    ```

    输出:

    ```cpp
    Strings are equal
    ```** 
*   ****查找(“字符串”):**在字符串中搜索参数中指定的子字符串的第一次出现。它返回子字符串第一次出现的位置。**
*   ****find_first_of("字符串"):**在字符串中搜索与参数中指定的任何字符匹配的第一个字符。它返回匹配的第一个字符的位置。**
*   ****find_last_of(“字符串”):**在字符串中搜索与参数中指定的任何字符匹配的最后一个字符。它返回匹配的最后一个字符的位置。**
*   ****rfind(“string”):** Searches the string for the last occurrence of the substring specified in arguments. It returns the position of the last occurrence of substring

    ```cpp
    // C++ program to demonstrate working of find(),
    // rfind(),find_first_of() and find_last_of()
    #include<iostream>
    #include<string>
    using namespace std;
    int main()
    {
        string str("The Geeks for Geeks");

        // find() returns position to first
        // occurrence of substring "Geeks"
        // Prints 4
        cout << "First occurrence of \"Geeks\" starts from : ";
        cout << str.find("Geeks") << endl;

        // Prints position of first occurrence of
        // any character of "reef" (Prints 2)
        cout << "First occurrence of character from \"reef\" is at : ";
        cout << str.find_first_of("reef") << endl;

        // Prints position of last occurrence of
        // any character of "reef" (Prints 16)
        cout << "Last occurrence of character from \"reef\" is at : ";
        cout << str.find_last_of("reef") << endl;

        // rfind() returns position to last
        // occurrence of substring "Geeks"
        // Prints 14
        cout << "Last occurrence of \"Geeks\" starts from : ";
        cout << str.rfind("Geeks") << endl;

        return 0;

    }
    ```

    输出:

    ```cpp
    First occurrence of "Geeks" starts from : 4
    First occurrence of character from "reef" is at : 2
    Last occurrence of character from "reef" is at : 16
    Last occurrence of "Geeks" starts from : 14

    ```** 
*   ****insert(pos_to_begin,string_to_insert):** This function inserts the given substring in the string. It takes two arguments, first the position from which you want to insert the substring and second the substring.

    ```cpp
    // C++ program to demonstrate working of insert()
    #include<iostream>
    #include<string>
    using namespace std;
    int main()
    {
        string str("Geeksfor");

        // Printing the original string
        cout << str << endl;

        // Inserting "Geeks" at 8th index position
        str.insert(8,"Geeks");

        // Printing the modified string
        // Prints "GeeksforGeeks"
        cout << str << endl;

        return 0;
    }
    ```

    输出:

    ```cpp
    Geeksfor
    GeeksforGeeks

    ```** 
*   ****clear():** 该函数清除字符串中的所有字符。执行此操作后，字符串变为空(长度变为 0)。**
*   ****empty():** Tests whether the string is empty. This function return a Boolean value.

    ```cpp
    // C++ program to demonstrate working of clear()
    // and empty()
    #include<iostream>
    #include<string>
    using namespace std;
    int main()
    {
        string str("GeeksforGeeks");

        // clearing string
        str.clear();

        // Checking if string is empty
        (str.empty()==1)?
             cout << "String is empty" << endl:
             cout << "String is not empty" << endl;

        return 0;

    }
    ```

    输出:

    ```cpp
    String is empty

    ```** 

**本文由**曼吉特·辛格供稿。**如果你喜欢 GeeksforGeeks 并且愿意投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论**