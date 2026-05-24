# std::string::append()在 C++ 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdstring append-in-c/

此成员函数在字符串末尾追加字符。

1.  **Syntax 1 :** Appends the characters of string str. It Throws length_error if the resulting size exceeds the maximum number of characters.

    ```cpp
    string& string::append (const string& str) 
    str :  is the string to be appended.
    Returns :  *this
    ```

    ```cpp
    // CPP code to demonstrate append(str)

    #include <iostream>
    #include <string>
    using namespace std;

    // Function to demonstrate append()
    void appendDemo(string str1, string str2)
    {
        // Appends str2 in str1
        str1.append(str2);
        cout << "Using append() : ";
        cout << str1 << endl;
    }

    // Driver code
    int main()
    {
        string str1("Hello World! ");
        string str2("GeeksforGeeks");

        cout << "Original String : " << str1 << endl;
        appendDemo(str1, str2);

        return 0;
    }
    ```

    输出:

    ```cpp
    Original String : Hello World! 
    Using append() : Hello World! GeeksforGeeks

    ```

2.  **Syntax 2 :** Appends at most, str_num characters of string str, starting with index str_idx. It throws out_of_range if str_idx > str. size(). It throws length_error if the resulting size exceeds the maximum number of characters.

    ```cpp
    string& string::append (const string& str, size_type str_idx, size_type str_num)

    str : is the string to be appended
    str_num : being number of characters
    str_idx : is index number.
    Returns : *this.

    ```

    ```cpp
    // CPP code to demonstrate 
    // append(const char* chars, size_type chars_len)

    #include <iostream>
    #include <string>
    using namespace std;

    // Function to demonstrate append()
    void appendDemo(string str1, string str2)
    {
        // Appends 5 characters from 0th index of
        // str2 to str1
        str1.append(str2, 0, 5);
        cout << "Using append() : ";
        cout << str1;
    }

    // Driver code
    int main()
    {
        string str1("GeeksforGeeks ");
        string str2("Hello World! ");

        cout << "Original String : " << str1 << endl;
        appendDemo(str1, str2);

        return 0;
    }
    ```

    输出:

    ```cpp
    Original String : GeeksforGeeks 
    Using append() : GeeksforGeeks Hello

    ```

3.  **Syntax 3:** Appends the characters of the C-string cstr. Throw length_error if the resulting size exceeds the maximum number of characters.

    ```cpp
    string& string::append (const char* cstr)

    *cstr : is the pointer to C-string.
    Note : that cstr may not be a null pointer (NULL).
    Return : *this

    ```

    ```cpp
    // CPP code to demonstrate append(const char* cstr)

    #include <iostream>
    #include <string>
    using namespace std;

    // Function to demonstrate append
    void appendDemo(string str)
    {
        // Appends "GeeksforGeeks"
        // in str
        str.append("GeeksforGeeks");
        cout << "Using append() : ";
        cout << str << endl;
    }

    // Driver code
    int main()
    {
        string str("World of ");

        cout << "Original String : " << str << endl;
        appendDemo(str);

        return 0;
    }
    ```

    输出:

    ```cpp
    Original String : World of 
    Using append() : World of GeeksforGeeks

    ```

4.  **Syntax 4:** Appends chars_len characters of the character array chars. Throws length_error if the resulting size exceeds the maximum number of characters.

    ```cpp
    string& string::append (const char* chars, size_type chars_len)

    *chars is the pointer to character array to be appended.
    chrs_len : is the number of characters from *chars to be appended.
    Note that chars must have at least chars_len characters. 
    Returns : *this.

    ```

    ```cpp
    // CPP code to demonstrate 
    // (const char* chars, size_type chars_len)

    #include <iostream>
    #include <string>
    using namespace std;

    // Function to demonstrate append
    void appendDemo(string str)
    {
        // Appends 5 characters from "GeeksforGeeks"
        // to str
        str.append("GeeksforGeeks", 5);
        cout << "Using append() : ";
        cout << str << endl;
    }

    // Driver code
    int main()
    {
        string str("World of ");

        cout << "Original String : " << str << endl;
        appendDemo(str);

        return 0;
    }
    ```

    输出:

    ```cpp
    Original String : World of 
    Using append() : World of Geeks

    ```

5.  **Syntax 5:** Appends num occurrences of character c. Throws length_error if the resulting size exceeds the maximum number of characters.

    ```cpp
    string& string::append (size_type num, char c)

    num : is the number of occurrences
    c : is the character which is to be appended repeatedly. 
    Returns : *this.

    ```

    ```cpp
    // CPP code to illustrate
    // string& string::append (size_type num, char c)

    #include <iostream>
    #include <string>
    using namespace std;

    // Function to demonstrate append
    void appendDemo(string str)
    {
        // Appends 10 occurrences of '{content}apos;
        // to str
        str.append(10, '{content}apos;);
        cout << "After append() : ";
        cout << str;

    }

    // Driver code
    int main()
    {
        string str("#########");

        cout << "Original String : " << str << endl;
        appendDemo(str);

        return 0;
    }
    ```

    输出:

    ```cpp
    Original String : #########
    After append() : #########$$$$$

    ```

6.  **Syntax 6:** Appends all characters of the range [beg, end). Throws length_error if the resulting size exceeds the maximum number of characters.

    ```cpp
    string& string::append (InputIterator beg, InputIterator end)

    first, last : Input iterators to the initial and final positions 
    in a sequence.
    Returns *this.

    ```

    ```cpp
    // CPP code  to illustrate
    // append (InputIterator beg, InputIterator end)

    #include <iostream>
    #include <string>
    using namespace std;

    // Function to demonstrate append
    void appendDemo(string str1, string str2)
    {

        // Appends all characters from
        // str2.begin()+5, str2.end() to str1
        str1.append(str2.begin() + 5, str2.end());
        cout << "Using append : ";
        cout << str1;
    }
    // Driver code
    int main()
    {
        string str1("Hello World! ");
        string str2("GeeksforGeeks");

        cout << "Original String : " << str1 << endl;
        appendDemo(str1, str2);

        return 0;
    }
    ```

    输出:

    ```cpp
    Original String : Hello World! 
    Using append : Hello World! forGeeks

    ```

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。