# C/c++ 中的 ctype.h( <cctype>)库，示例</cctype>

> 原文:[https://www . geesforgeks . org/ctype-hcctype-library-in-c-c-with-examples/](https://www.geeksforgeeks.org/ctype-hcctype-library-in-c-c-with-examples/)

由于 **[string.h](https://www.geeksforgeeks.org/commonly-used-string-functions-in-c-c-with-examples/)** 头文件包含处理 C/C++ 中字符串的内置函数，**ctype . h**/**<cctype>**包含分别处理 C/C++ 中字符的内置函数。

字符有两种类型:

1.  **可打印字符:**显示在终端上的字符。
2.  **控制字符:**开始执行特定操作的字符。

传递给字符函数的参数应为整数类型。如果我们传递字符而不是整数，字符将被类型化为整数(对应的 ASCII 值)，这些整数将作为参数传递。

**ctype . h**/**<cctype>**头文件下的以下功能应用于普通字符。宽字符功能用于类型 [wchar_t](https://www.geeksforgeeks.org/wide-char-and-library-functions-in-c/) 的字符。

| S.No | 功能 | 描述 | 返回值 |
| --- | --- | --- | --- |
| 1. | [【is lnum()](https://www.geeksforgeeks.org/isalnum-function-c-language/) | 该功能识别字母数字字符 | 如果传递的参数是非字母数字字符
，则返回 0；如果传递的参数是字母数字字符，则返回非零值 |
| 2. | [异α（）](https://www.geeksforgeeks.org/isalpha-isdigit-functions-c-example/) | 该功能将字母与其他字符区分开来 | 如果传递的参数不是字母表
则返回 0，如果传递的参数是字母表，则返回非零值 |
| 3. | [【ISBN()](https://www.geeksforgeeks.org/isblank-in-cc/) | 该函数将空格与其他字符区分开 | 如果传递的参数不是空格
则返回 0，如果传递的参数是空格则返回非零值 |
| 4. | iscl() | 该函数识别控制字符(\n，b，t，r)。 | 如果传递的参数不是控制字符
，则返回 0；如果传递的参数是控制字符，则返回非零值 |
| 5. | [isdigital()](https://www.geeksforgeeks.org/isalpha-isdigit-functions-c-example/) | 该功能识别字符中的数字。 | 如果传递的参数不是数字
，则返回 0；如果传递的参数是数字，则返回非零值 |
| 6. | [岛电()](https://www.geeksforgeeks.org/isupper-islower-application-c/) | 这个函数识别小写字母。 | 如果传递的参数不是小写字母
则返回 0，如果传递的参数是小写字母则返回非零值 |
| 7. | [打印 （）](https://www.geeksforgeeks.org/isprint-in-c/) | 该功能识别可打印字符。 | 如果传递的参数是不可打印字符
，则返回 0；如果传递的参数是可打印字符，则返回非零值 |
| 8. | [ispunct（）](https://www.geeksforgeeks.org/ispunct-function-c/) | 该功能识别标点字符(既不是字母数字也不是空格的字符)。 | 如果传递的参数不是标点符号
，则返回 0；如果传递的参数是标点符号，则返回非零值 |
| 9. | [这种空间()](https://www.geeksforgeeks.org/isspace-in-c-and-its-application-to-count-whitespace-characters/) | 该函数识别空白字符。 | 如果传递的参数不是空白字符
，则返回 0；如果传递的参数是空白字符，则返回非零值 |
| 10. | [isupper()](https://www.geeksforgeeks.org/isupper-islower-application-c/) | 该函数识别大写字母。 | 如果传递的参数不是大写字母
，则返回 0；如果传递的参数是大写字母，则返回非零值 |
| 11. | [isxdigit()](https://www.geeksforgeeks.org/isxdigit-function-c-language/) | 该函数识别十六进制数字。 | 如果传递的参数不是十六进制数字
，则返回 0；如果传递的参数是十六进制数字，则返回非零值 |
| 12. | tolpower() | 这个函数把大写字母转换成小写字母。 | 返回相应大写字母的小写字母 |
| 13. | [toupper()](https://www.geeksforgeeks.org/toupper-function-in-c/) | 这个函数把小写字母转换成大写字母。 | 返回相应小写字母的大写字母 |

以下是实现上述一些功能的示例:

*   **例 1:** 以下程序识别字母、数字的个数:

    ```cpp
    #include <stdio.h>

    // Header file containing character functions
    #include <ctype.h>

    void identify_alpha_numeric(char a[])
    {
        int count_alpha = 0, count_digit = 0;
        for (int i = 0; a[i] != '\0'; i++) {
            // To check the character is alphabet
            if (isalpha(a[i]))
                count_alpha++ ;

            // To check the character is a digit
            if (isdigit(a[i]))
                count_digit++ ;
        }
        printf("The number of alphabets are %d\n",
               count_alpha);
        printf("The number of digits are %d",
               count_digit);
    }

    int main()
    {
        // String Initialization
        char a[]
            = "Hi 1234, "
              " Welcome to GeeksForGeeks";
        identify_alpha_numeric(a);
    }
    ```

    **输出:**

    ```cpp
    The number of alphabets are 24
    The number of digits are 4

    ```

*   **示例 2:** 以下程序识别大写字母和小写字母的数量，并将大写字母转换为小写:

    ```cpp
    #include <stdio.h>

    // Header file containing character functions
    #include <ctype.h>

    char* identify_convert_ul(char a[])
    {
        int count_upper = 0, count_lower = 0;
        for (int i = 0; a[i] != '\0'; i++) {

            // To check the uppercase characters
            if (isupper(a[i])) {
                count_upper++ ;
                a[i] = tolower(a[i]);
            }

            // To check the lowercase characters
            else if (islower(a[i])) {
                count_lower++ ;
                a[i] = toupper(a[i]);
            }
        }
        printf("No. of uppercase characters are %d\n",
               count_upper);
        printf("No. of lowercase characters are %d",
               count_lower);
        return a;
    }

    int main()
    {
        // String Initialization
        char a[] = "Hi, Welcome to GeeksForGeeks";
        char* p;
        p = identify_convert_ul(a);
        printf("%s", p);
    }
    ```

    **输出:**

    ```cpp
    No. of uppercase alphabets are 5
    No. of lowercase alphabets are 19
    hI, wELCOME TO gEEKSfORgEEKS

    ```

*   **示例 3:** 以下程序打印新行中的每个单词:

    ```cpp
    #include <stdio.h>

    // Header file containing character functions
    #include <ctype.h>

    char* print_word(char a[])
    {
        for (int i = 0; a[i] != '\0'; i++) {

            // Space is replaced
            // with control character '\n'
            if (isblank(a[i]))
                a[i] = '\n';
        }
        return a;
    }
    int main()
    {
        // String Initialization
        char a[] = "Hello Everyone."
                   " Welcome to GeeksForGeeks portal. ";
        char* p;
        p = print_word(a);
        printf("%s", p);
    }
    ```

    **输出:**

    ```cpp
    Hello
    Everyone.
    Welcome
    to
    GeeksForGeeks
    portal.

    ```