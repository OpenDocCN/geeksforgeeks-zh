# C/c++

中的 strcoll()

> 原文:[https://www.geeksforgeeks.org/strcoll-in-cc/](https://www.geeksforgeeks.org/strcoll-in-cc/)

**strcoll()** 是内置库函数，在 **< string.h >** 头文件中声明。该功能将 *str1* 指向的字符串与 *str2* 指向的字符串进行比较。 **strcoll()** 函数根据当前地区的 **LC_COLLATE** 类别的规则执行比较。
**语法:**

```cpp
int strcoll(const char *str1, const char *str2)
```

**参数:**函数 strcoll()取两个字符串作为参数，返回一个整数值。

```cpp
Value                   Meaning
less than zero         * str1* is less than *str2*
zero                   * str1* is equal to *str2*
greater than zero      * str1* is greater than *str2*
```

1.  **less than zero :** When *str1* is less than *str2*

    ```cpp
    // C program to illustrate strcoll()
    #include <stdio.h>
    #include <string.h>

    int main()
    {
        char str1[10];
        char str2[10];
        int ret;

        strcpy(str1, "geeksforgeeks");
        strcpy(str2, "GEEKSFORGEEKS");

        ret = strcoll(str1, str2);

        if (ret > 0) {
            printf("str1 is greater than str2");
        } else if (ret < 0) {
            printf("str1 is lesser than str2");
        } else {
            printf("str1 is equal to str2");
        }

        return (0);
    }
    ```

    **输出:**

    ```cpp
    str1 is greater than str2

    ```

2.  **greater than zero :**when *str1* is greater than *str2*

    ```cpp
    // C program to illustrate strcoll()
    #include <stdio.h>
    #include <string.h>

    int main()
    {
        char str1[10];
        char str2[10];
        int ret;

        strcpy(str1, "GEEKSFORGEEKS");
        strcpy(str2, "geeksforgeeks");

        ret = strcoll(str1, str2);

        if (ret > 0) {
            printf("str1 is greater than str2");
        } else if (ret < 0) {
            printf("str1 is lesser than str2");
        } else {
            printf("str1 is equal to str2");
        }

        return (0);
    }
    ```

    **输出:**

    ```cpp
    str1 is lesser than str2

    ```

3.  **Is equal to zero :** when *str1* is equal to *str2*

    ```cpp
    // C program to illustrate strcoll()

    #include <stdio.h>
    #include <string.h>

    int main()
    {
        char str1[10];
        char str2[10];
        int ret;

        strcpy(str1, "GEEKSFORGEEKS");
        strcpy(str2, "GEEKSFORGEEKS");

        ret = strcoll(str1, str2);

        if (ret > 0) {
            printf("str1 is greater than str2");
        } else if (ret < 0) {
            printf("str1 is lesser than str2");
        } else {
            printf("str1 is equal to str2");
        }

        return (0);
    }
    ```

    **输出:**

    ```cpp
    str1 is equal to str2

    ```

相关功能:**[strcmp()](https://www.geeksforgeeks.org/strcmp-in-c-cpp/)[memcmp()](https://www.geeksforgeeks.org/stdmemcmp-in-cpp/)T5】**

本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。