# C/c++ 中的整数文字(前缀和后缀)

> 原文:[https://www . geesforgeks . org/integer-literal-in-c-CPP-前缀-后缀/](https://www.geeksforgeeks.org/integer-literal-in-c-cpp-prefixes-suffixes/)

整数文字是整数的文字类型，其值直接在源代码中表示。例如，在赋值语句 **x = 1** 中，字符串 1 是表示值 1 的整数文字，而在语句 **x = 0x10** 中，字符串 *0x10* 是表示值 16(以十进制表示)的整数文字，以十六进制的 10(以 0x 前缀表示)表示。
此外，在 **x = "1"** 中，“1”是字符串文字(不是字符或整数文字)，因为它在引号中。字符串的值是 1，恰好是一个整数字符串。

**整数文字有两种表达方式，即**

1.  **前缀**表示基数。例如， **0x10** 表示十六进制值 *16* ，前缀为 **0x** 。
2.  **后缀**表示类型。例如， **12345678901234LL** 表示值 *12345678901234* 为长整型，后缀为 **LL** 。

**语法**

*   **前缀:**它们基本上以四种类型表示。

1.  **十进制-文字(以 10 为基数)** :-一个非零十进制数字，后跟零个或多个十进制数字(0、1、2、3、4、5、6、7、8、9)。比如 *56、78* 。
2.  **八进制文字(以 8 为基数)** :-零后跟零个或多个八进制数字(0、1、2、3、4、5、6、7)。例如 *045，076，06210* 。
3.  **十六进制文字(以 16 为基数)** :- 0x 或 0x 后跟一个或多个十六进制数字(0、1、2、3、4、5、6、7、8、9、A、B、B、C、C、D、D、E、E、F、F)。例如 *0x23A、0Xb4C、0xfa*。
4.  **二进制文字(基数 2)** :- 0b 或 0b 后跟一个或多个二进制数字(0，1)。例如 *0b101，0B111* 。

*   **Suffixes:** They are represented in many ways according to their data types.
    1.  **int** :-不需要后缀，因为整数常量默认分配为 int 数据类型。
    2.  **无符号整数**:整数常量末尾的字符 **u 或 U** 。
    3.  **长整型**:整数常量末尾的字符 **l 或 L** 。
    4.  **无符号长整型**:整数常量末尾的字符 **ul 或 UL** 。
    5.  **long long int** :整数常量末尾的字符 **ll 或 LL** 。
    6.  **无符号长整型**:整型常量末尾的字符 **ull 或 ULL** 。

    ```cpp
    // C++ program to demonstrate the use of
    // integer literal
    #include <iostream>
    using namespace std;

    int main()
    {
        // PREFIXES
        cout << 213   << '\n'  // decimal integer literal
             << 0213  << '\n'  // Octal integer literal
             << 0x213A << '\n' // hexadecimal integer literal
             << 0b101  << '\n' // binary integer literal

             // SUFFIXES
             // long long literal
             << 1234567890123456789LL << '\n'

             // unsigned long long literal
             << 12345678901234567890ull << '\n'

             // automatic conversion of unsigned long long even
             // without long long prefix
             << 12345678901234567890u;

        return 0;
    }
    ```

    ```cpp
    Output:
    213
    139
    8506
    5
    1234567890123456789
    12345678901234567890
    12345678901234567890
    1221300

    ```

    **数字分隔符:**在 C++ 中，整数文字可能包含数字分隔符，以允许数字分组为更易读的形式。这对于位字段特别有用，并且通过子排序而不是计数数字，可以更容易地一目了然地看到大数字(例如一百万)的大小。它对于通常分组的号码也很有用，例如信用卡号或社会保险号。[a]很长的数字可以通过加倍分隔符进一步分组。
    通常，十进制数(基数-10)分为三个数字组(代表 1000 个可能值中的一个)，二进制数(基数-2)分为四个数字组(一个半字节，代表 16 个可能值中的一个)，十六进制数(基数-16)分为两个数字组(每个数字是一个半字节，因此两个数字是一个字节，代表 256 个可能值中的一个)。来自其他系统的号码(如 id 号码)按照使用的惯例进行分组。

    ```cpp
    // C++ program to demonstrate digit separator
    #include <iostream>
    using namespace std;

    int main()
    {
        cout << 12345678901245LL <<'\n'

             // long long int literal digit separator
             << 12'345'678'901'245LL <<'\n'

             // binary literal digit separator
             << 0b1000'111'0 <<'\n'

             // hexadecimal literal digit separator
             << 0X12A'2b4;
             return 0;
    }
    ```

    ```cpp
    Output:
    12345678901245
    12345678901245
    142
    1221300

    ```

    **参考**:-[https://en.wikipedia.org/wiki/Integer_literal](https://en.wikipedia.org/wiki/Integer_literal)
    本文由[舒巴姆·班萨尔](https://www.quora.com/profile/Shubham-Bansal-209)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。