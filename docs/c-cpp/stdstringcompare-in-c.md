# std::string::compare()在 C++ 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdstringcompare-in-c/

**compare()** 是 string 类的公共成员函数。它将字符串对象(或子字符串)的值与其参数指定的字符序列进行比较。
compare()可以为每个字符串处理多个参数，这样就可以通过其索引和长度来指定子字符串。

**返回类型:** compare()返回整数值而不是布尔值。

**字符串的不同语法::compare() :**

1.  **Syntax 1:** Compares the string *this with the string str.

    ```cpp
    int string::compare (const string& str) const
    Returns:
    0 : if both strings are equal.
    A value **<** 0 : if *this is shorter than str or,
    first character that doesn't match is smaller than str.
    A value **>** 0 : if *this is longer than str or,
    first character that doesn't match is greater

    ```

    ```cpp
    // CPP code for demonstrating 
    // string::compare (const string& str) const

    #include<iostream>
    using namespace std;

    void compareOperation(string s1, string s2)
    {
        // returns a value < 0 (s1 is smaller then s2)
        if((s1.compare(s2)) < 0)
            cout << s1 << " is smaller than " << s2 << endl;

        // returns 0(s1, is being comapared to itself)
        if((s1.compare(s1)) == 0)
            cout << s1 << " is equal to " << s1 << endl;
        else
            cout << "Strings didn't match ";

    }

    // Driver Code
    int main()
    {
        string s1("Geeks");
        string s2("forGeeks");
        compareOperation(s1, s2);

        return 0; 
    }
    ```

    输出:

    ```cpp
    Geeks is smaller than forGeeks
    Geeks is equal to Geeks

    ```

2.  **Syntax 2:** Compares at most, len characters of string *this, starting with index idx with the string str.

    ```cpp
    int string::compare (size_type idx, size_type len, const string& str) const
    Throws out_of_range if index > size().

    ```

    ```cpp
    // CPP code to demonstrate 
    // int string::compare (size_type idx, size_type len, 
    // const string& str) const

    #include<iostream>
    using namespace std;

    void compareOperation(string s1, string s2)
    {
        // Compares 5 characters from index number 3 of s2 with s1
        if((s2.compare(3, 5, s1)) == 0)
            cout << "Here, "<< s1 << " are " << s2;

        else
            cout << "Strings didn't match ";
    }
    // Driver Code
    int main()
    {
        string s1("Geeks");
        string s2("forGeeks");
        compareOperation(s1, s2);

      return 0; 
    }
    ```

    输出:

    ```cpp
    Here, Geeks are forGeeks

    ```

3.  **Syntax 3:** Compares at most, len characters of string *this starting with index idx with at most, str_len characters of string str starting with index str_idx.

    ```cpp
    int string::compare (size_type idx, size_type len, const string& 
    str, size_type str_idx, size_type str_len) const
    Throws out_of_range if idx > size().
    Throws out_of_range if str_idx > str.size().

    ```

    ```cpp
    // CPP code to demonstrate 
    // int string::compare (size_type idx, size_type len, const string& 
    // str, size_type str_idx, size_type str_len) const

    #include<iostream>
    using namespace std;

    void compareOperation(string s1, string s2)
    {
        // Compares 5 characters from index number 0 of s1 with
        // 5 characters from index 3 of s2
        if((s1.compare(0, 5, s2, 3, 5)) == 0)
            cout << "Welcome to " << s1 << s2 << " World";

        else
            cout << "Strings didn't match ";
    }
    // Driver Code
    int main()
    {
        string s1("Geeks");
        string s2("forGeeks");
        compareOperation(s1, s2);

      return 0; 
    }
    ```

    输出:

    ```cpp
    Welcome, to GeeksforGeeks World

    ```

4.  **Syntax 4:** Compares the characters of string *this with the characters of the C-string cstr.

    ```cpp
    int string::compare (const char* cstr) const
    ```

    ```cpp
    // CPP code to demonstrate
    // int string::compare (const char* cstr) const

    #include<iostream>
    using namespace std;

    void compareOperation(string s1, string s2)
    {
        // returns < 0 (s1 < "GeeksforGeeks")
        if((s1.compare("GeeksforGeeks")) < 0)
            cout << s1 << " is smaller than string " << "GeeksforGeeks"; 

        //returns 0 (s2 is "forgeeks")
        if((s2.compare("forGeeks")) == 0)
            cout << endl << s2 << " is equal to string " << s2; 

        else
            cout << "Strings didn't match ";

    }
    // Driver Code
    int main()
    {
        string s1("Geeks");
        string s2("forGeeks");
        compareOperation(s1, s2);

      return 0; 
    }
    ```

    输出:

    ```cpp
    Geeks is smaller than string GeeksforGeeks
    forGeeks is equal to string forGeeks

    ```

5.  **Syntax 5:** Compares at most, len characters of string *this, starting with index idx with all characters of the C-string cstr.

    ```cpp
    int string::compare (size_type idx, size_type len, const char* cstr) const

    ```

    请注意，cstr 不能是空指针(null)。

    ```cpp
    // CPP code to demonstrate 
    // int string::compare (size_type idx, size_type len, 
    // const char* cstr) const
    #include<iostream>
    using namespace std;

    void compareOperation(string s1)
    {
        // Compares 5 characters from 0 index of s1 with "Geeks"
        if((s1.compare(0, 5, "Geeks")) == 0)
            cout << s1 << " are " << "awesome people"; 

        else
            cout << "Strings didn't match ";

    }

    // Driver Code
    int main()
    {
        string s1("Geeks");
        compareOperation(s1);

      return 0; 
    }
    ```

    输出:

    ```cpp
    Geeks are awesome people

    ```

6.  **Syntax 6:** Compares, at most, len characters of string *this, starting with index idx with chars_len characters of the character array chars.

    ```cpp
    int string::compare (size_type idx, size_type len, const char* chars, 
    size_type chars_len)const
    ```

    请注意，字符必须至少包含 chars_len 字符。字符可以有任意值。因此，' \0 '没有特殊含义。

    ```cpp
    // CPP code to demonstrate 
    // int string::compare (size_type idx, size_type len, 
    // const char* chars, size_type chars_len)const

    #include<iostream>
    using namespace std;

    void compareOperation(string s1, string s2)
    {
        // Compares 5 characters from 0 index of s1 with 
        // 5 characters of string "Geeks"
        if((s1.compare(0, 5, "Geeks", 5)) == 0)
            cout << "This is " << s1 <<  s2 ; 

        else
            cout << "Strings didn't match ";
    }

    // Driver Code
    int main()
    {
        string s1("Geeks");
        string s2("forGeeks");
        compareOperation(s1, s2);

      return 0; 
    }
    ```

    输出:

    ```cpp
    This is GeeksforGeeks

    ```

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。