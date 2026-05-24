# C/c++

中的 strcmp()

> 原文:[https://www.geeksforgeeks.org/strcmp-in-c-cpp/](https://www.geeksforgeeks.org/strcmp-in-c-cpp/)

strcmp()是一个内置库函数，在 **< string.h >** 头文件中声明。该函数将两个字符串作为参数，并按字典顺序比较这两个字符串。

**语法:**:

```cpp
int strcmp(const char *leftStr, const char *rightStr );

```

在上面的原型中，函数 srtcmp 将两个字符串作为参数，并基于字符串的比较返回一个整数值。

*   strcmp()按字典顺序比较**两个字符串**表示它从第一个字符开始逐字符比较，直到两个字符串中的字符相等或遇到空字符。
*   如果两个字符串中的第一个字符相等，那么这个函数将检查第二个字符，如果这个字符也相等，那么它将检查第三个字符，以此类推
*   这一过程将继续，直到任一字符串中的字符为空或字符不相等。

**strcmp()返回什么？**

该函数可以根据比较结果返回**三个不同的整数值**:

1.  **Zero ( 0 )**: A value equal to zero when both strings are found to be identical. That is, That is, All of the characters in both strings are same.

    ```cpp
    All characters of strings are same
    ```

    ```cpp
    // C program to illustrate
    // strcmp() function
    #include<stdio.h>
    #include<string.h>

    int main()
    { 

        char leftStr[] = "g f g";
        char rightStr[] = "g f g";

        // Using strcmp()
        int res = strcmp(leftStr, rightStr);

        if (res==0)
            printf("Strings are equal");
        else 
            printf("Strings are unequal");

        printf("\nValue returned by strcmp() is:  %d" , res);
        return 0;
    }
    ```

    输出:

    ```cpp
    Strings are equal
    Value returned by strcmp() is:  0

    ```

2.  **Greater than zero ( >0 )**: A value greater than zero is returned when the first not matching character in leftStr have the greater ASCII value than the corresponding character in rightStr or we can also say

    ```cpp
    If character in leftStr is lexicographically
    after the character of rightStr 
    ```

    ```cpp
    // C program to illustrate
    // strcmp() function
    #include<stdio.h>
    #include<string.h>
    int main()
    { 
        // z has greater ASCII value than g
        char leftStr[] = "zfz";
        char rightStr[] = "gfg";

        int res = strcmp(leftStr, rightStr);

        if (res==0)
            printf("Strings are equal");
        else 
            printf("Strings are unequal");

        printf("\nValue of result: %d" , res);

        return 0;
    }
    ```

    输出:

    ```cpp
    Strings are unequal
    Value returned by strcmp() is:  19

    ```

3.  **Less than Zero ( <0 )**: A value less than zero is returned when the first not matching character in leftStr have lesser ASCII value than the corresponding character in rightStr.

    ```cpp
    If character in leftStr is lexicographically
    before the character of rightStr
    ```

    ```cpp
    // C program to illustrate
    // strcmp() function
    #include<stdio.h>
    #include<string.h>
    int main()
    { 
        // b has less ASCII value than g
        char leftStr[] = "bfb";
        char rightStr[] = "gfg";

        int res = strcmp(leftStr, rightStr);

        if (res==0)
            printf("Strings are equal");
        else 
            printf("Strings are unequal");

        printf("\nValue returned by strcmp() is:  %d" , res);

        return 0;
    }
    ```

    输出:

    ```cpp
    Strings are unequal
    Value returned by strcmp() is:  -5

    ```

    **重要提示:**当字符串不同时，你会发现 strcmp()函数返回的值是两种情况下 leftStr 和 rightStr 中第一个不匹配字符的 ASCII 值之差。

    本文由**严酷阿加瓦尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。