# std::stod，std::stof，std::stold 在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdstod-stdstof-stdstold-c/](https://www.geeksforgeeks.org/stdstod-stdstof-stdstold-c/)

1.  **std::stod() :** It convert string into double.
    Syntax:

    ```cpp
    double stod( const std::string& str, std::size_t* pos = 0 );
    double stod( const std::wstring& str, std::size_t* pos = 0 );
    Return Value: return a value of type double
    Parameters
    str : the string to convert
    pos : address of an integer to store the 
    number of characters processed. This parameter can also be 
    a null pointer, in which case it is not used.

    ```

    ```cpp
    // CPP program to illustrate
    // std::stod()
    #include <string>
    #include <iostream>

    int main(void)

    {
        std::string str = "y=4.4786754x+5.6";

        double y, x, a, b;
        y = 0;
        x = 0;

        // offset will be set to the length of 
        // characters of the "value" - 1.
        std::size_t offset = 0;

        a = std::stod(&str[2], &offset);
        b = std::stod(&str[offset + 3]);

        std::cout << b;
        return 0;
    }
    ```

    输出:

    ```cpp
    5.6

    ```

    **另一个例子:**

    ```cpp
    // CPP program to illustrate
    // std::stod()
    #include <iostream>
    #include <string>
    using namespace std;
    int main()
    {

        string b = "5";
        double a = stod(b);
        int c = stoi(b);
        cout << b << " " << a << " " << c << endl;
    }
    ```

    输出:

    ```cpp
    5 5 5

    ```

    如果不执行转换，将引发 invalid_argument 异常。如果读取的值超出了双精度值可表示的范围，则会引发超出范围异常。无效的 idx 会导致未定义的行为。

2.  **std::stof :** It convert string into float.
    Syntax:

    ```cpp
    float stof( const string& str, size_t* pos = 0 );
    float stof( const wstring& str, size_t* pos = 0 );
    Parameters
    str : the string to convert
    pos : address of an integer to store the number of characters processed
    This parameter can also be a null pointer, in which case it is not used.
    Return value: it returns value of type float.
    ```

    **例 1:**

    ```cpp
    // CPP program to illustrate
    // std::stof()
    #include <iostream>
    #include <string>
    int main()
    {
        std::string x;
        x = "20";
        float y = std::stof(x) + 2.5;
        std::cout << y;
        return 0;
    }
    ```

    输出:

    ```cpp
    22.5

    ```

    **例 2:**

    ```cpp
    // CPP program to illustrate
    // std::stof()
    #include <iostream>
    #include <string>
    int main()
    {
        std::string str = "5000.5";
        float x = std::stof(str);
        std::cout << x;
        return 0;
    }
    ```

    **输出:**

    ```cpp
    5000.5

    ```

    如果无法执行转换，将引发无效的参数异常。

3.  **std::stold :** It convert string into long double.
    Syntax:

    ```cpp
    long double stold( const string& str, size_t *pos = 0 );
    long double stold (const wstring& str, size_t* pos = 0);
    Parameters : 
    str : the string to convert
    pos : address of integer to store the index of the first unconverted character.
    This parameter can also be a null pointer, in which case it is not used.
    Return value : it returns value of type long double.

    ```

    **实施例 1:**

    ```cpp
    // CPP program to illustrate
    // std::stold()
    #include <iostream>
    #include <string>
    int main()
    {
        std::string str = "500087";
        long double x = std::stold(str);
        std::cout << x;
        return 0;
    }
    ```

    输出:

    ```cpp
    500087

    ```

    **例 2:**

    ```cpp
    // CPP program to illustrate
    // std::stold()
    #include <iostream>
    #include <string>
    int main()
    {
        std::string x;
        x = "2075";
        long double y = std::stof(x) + 2.5;
        std::cout << y;
        return 0;
    }
    ```

    输出:

    ```cpp
    2077.5

    ```

本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。