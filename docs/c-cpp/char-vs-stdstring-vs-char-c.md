# char * vs STD:c++ 中字符串 vs char[]

> 原文:[https://www.geeksforgeeks.org/char-vs-stdstring-vs-char-c/](https://www.geeksforgeeks.org/char-vs-stdstring-vs-char-c/)

在本文中，我们将检查 C++ 中初始化字符串的三种不同方式，并讨论它们之间的差异。

**1。使用 char***

这里，str 基本上是指向(const)字符串文字的指针。
**语法:**

```cpp
char* str = "This is GeeksForGeeks";
```

**优点:**

1.  引用整个字符串只需要一个指针。这表明这是内存高效的。
2.  不需要事先声明字符串的大小。

```cpp
// CPP program to illustrate *char
#include <iostream>
using namespace std;

int main()
{
    // pointer str points to const string literal "Hello".
    // No need to declare size.
    char* str1 = "This is GeeksForGeeks";

    cout << str1 << endl;

    int size = 30;

    // can allocate size dynamically.
    char* str2 = (char*)malloc(sizeof(char) * size);

    str2 = "GeeksForGeeks For Everyone";

    cout << str2;

    return 0;
}
```

**输出:**

```cpp
This is GeeksForGeeks
GeeksForGeeks For Everyone
```

cons:t1]

1.  这在 C 中可以很好地工作，但是在 C++ 中用这种形式编写是一个坏主意。这就是为什么编译器显示“不赞成从字符串常量转换为‘char *’”的警告
    ，因为在 C 语言中，字符串文字是字符数组，而在 C++ 中
    是字符常量数组。因此在 char*前使用 **const** 关键字。

    ```cpp
    const char* str = "This is GeeksForGeeks";
    ```

2.  We cannot modify the string at later stage in program. We can change str to point something else but cannot change value present at str. Refer [storage-for-strings-in-c](https://www.geeksforgeeks.org/storage-for-strings-in-c/) for more detail.

    ```cpp
    // CPP program to illustrate assigning
    // *char value to other variable 
    #include <iostream>
    using namespace std;

    int main()
    {
        // This initialization gives warning in C++.
        // "deprecated conversion from string constant
        // to 'char*'"
        char* str = "Hello";

        const char* str1 = "Hello"; // No warning

        // trying to modify const string literal
        // gives Runtime error
        str[1] = 'o';

        cout << str << endl;

        return 0;
    }
    ```

    **输出:**

    ```cpp
    Segmentation Fault
    ```

**2。使用[标准::字符串](https://www.geeksforgeeks.org/stdstring-class-in-c/)T3】**

**语法:**

```cpp
std::string str = "This is GeeksForGeeks";
```

这里 str 是 std::string 类的对象，它是使用 char(即字节)作为其字符类型的 **basic_string** 类模板的实例。

**注意:**在用 std::string 关键字声明字符串时，不要使用 **cstring** 或 **string.h** 函数，因为 **std::string** 字符串是 basic_string 类类型，cstring 字符串是 const char*类型。
**优点:**
在 C++ 中独占交易时 **std:string** 是最好的选择，因为它有更好的搜索、替换和操作功能。
下面讨论一些有用的 std:string 函数。

```cpp
// CPP program to illustrate 
// std::string functions
#include <iostream>
using namespace std;

int main()
{
    // string assignment
    string s1 = "Hello";
    string s2 = "World";

    // return length of string
    cout << s1.size() << endl; // 5
    cout << s2.length() << endl; // 5

    // concatenate string using + operator.
    s1 = s1 + s2;
    cout << s1 << endl; // HelloWorld

    // append string
    s1.append("Geeks");
    cout << s1 << endl; // HelloWorldGeeks

    string s3 = "HelloWorldGeeks";

    // compare two strings
    if (s1.compare(s3) == 0)
        cout << "true" << endl;
    else
        cout << "false" << endl;

    // substring of string s1
    // substr(pos, length_of_substring)
    string sub = s1.substr(0, 5);
    cout << sub << endl; // Hello

    // insert into string
    // insert(pos, string)
    s1.insert(10, "For");
    cout << s1 << endl; // HelloWorldForGeeks

    string target = "World";

    // find a target string in s1
    size_t pos = s1.find(target);
    if (pos != std::string::npos) // npos=-1
        cout << "Found at Position:" << pos << endl; // pos=5

    // replace a portion of string s1
    // replace(pos, length_of_portion, string_to_replace)
    cout << s1.replace(5, 5, "Geeks") << endl; // HelloGeeksForGeeks

    return 0;
}
```

**输出:**

```cpp
5
5
HelloWorld
HelloWorldGeeks
true
Hello
HelloWorldForGeeks
Found at Position:5
HelloGeeksForGeeks
```

**您可能更喜欢 char*而不是 std:string** 的情况

1.  当处理较低级别的访问时，比如与操作系统对话，但是通常，如果您将字符串传递给
    操作系统，那么 std::string::c_str 会覆盖它。
2.  与旧 C 代码的兼容性(尽管 std::string 的 c_str()方法处理了其中的大部分)。
3.  为了节省内存(std::string 可能会有更多开销)。

**3。使用 char[]**

**语法:**

```cpp
char str[] = "This is GeeksForGeeks";
     or 
char str[size] = "This is GeeksForGeeks";
//  Here str is a array of characters denoting the string.

```

**优点:**

1.  我们可以在程序的后期修改字符串。

```cpp
// CPP program to illustrate char
#include <iostream>
using namespace std;

int main()
{

    char str[] = "Hello";
    // or char str1[]={'H', 'e', 'l', 'l', 'o', '\0'};

    // modify string to "Hollo"
    str[1] = 'o';

    cout << str << endl;

    return 0;
}
```

**输出:**

```cpp
Hollo
```

cons:t1]

1.  这是静态分配大小的数组，消耗堆栈中的空间。
2.  We need to take the large size of array if we want to concatenate or manipulate with other strings since the size of string is fixed. We can use C++ standard library **cstring** or **string.h** for that purpose.

    ```cpp
    // CPP program to illustrate char
    // concatenation using standard functions
    #include <iostream>
    #include <cstring>
    using namespace std;

    int main()
    {
        // take large size of array
        char str[10] = "Hello";

        cout << "Before Concatenation : " << str << endl; // Hello
        strcat(str, " World");
        cout << "After Concatenation : " << str; // Hello World

        return 0;
    }
    ```

    输出:

    ```cpp
    Before Concatenation : Hello
    After Concatenation : Hello World

    ```

下面是 C++ 标准库的其他一些有用的函数。

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main()
{
    char s1[10] = "Hello";

    // return length of s1
    cout << strlen(s1) << endl;

    char s2[50];

    // copies s1 into s2
    strcpy(s2, s1);
    cout << s2 << endl;

    char s3[10] = "World";

    // concatenates s3 into s2
    strcat(s2, s3);
    cout << s2 << endl;

    char s4[50] = "HelloWorld";

    // return 0 if s2 and s4 are equal.
    if (strcmp(s2, s4) == 0)
        cout << "true" << endl;
    else
        cout << "false" << endl;

    char s5[30];

    // copies first 5 chars of s2 into s1
    strncpy(s5, s4, 5);
    cout << s5 << endl;

    char target[10] = "Hello";

    // search for target string in s4
    if (strstr(s4, target) != NULL)
        cout << "true" << endl;
    else
        cout << "false" << endl;

    return 0;
}
```

**输出:**

```cpp
5
Hello
HelloWorld
true
Hello
true
```

本文由 **Kshitiz Gupta** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。