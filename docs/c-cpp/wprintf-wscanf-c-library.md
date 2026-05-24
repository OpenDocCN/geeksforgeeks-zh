# C 库中的 wprintf()和 wscanf

> 原文:[https://www.geeksforgeeks.org/wprintf-wscanf-c-library/](https://www.geeksforgeeks.org/wprintf-wscanf-c-library/)

如果您正在处理宽字符，则不能使用 printf()和 scanf()函数。输入和输出 c 宽字符串有不同的函数。

1.  **wprintf() :** The wprintf() function writes the wide string pointed to by format to stdout. The wide string format may contain format specifiers starting with % which are replaced by the values of variables that are passed to the wprintf() function as additional arguments.

    **语法:**

    ```cpp
    int wprintf (const wchar_t* format, ...);
    ```

    **参数:**

    *   **格式:**指向写入 stdout 的空终止宽字符串的指针。它由宽字符以及以%开头的可选格式说明符组成。格式说明符被遵循格式的各个变量的值替换。
    *   **……:**其他指定要打印的数据的附加参数。它们按照格式说明符的顺序出现。这些参数的数量至少应该与格式说明符中指定的值的数量一样多。函数会忽略其他参数。
    *   **返回值:**如果成功，wprintf()函数返回写入的字符数。失败时，它返回负值。如果成功，wprintf()函数返回写入的字符数。
        失败时返回负值。

    ```cpp
    // C Program to show the wprintf () function.
    #include <stdio.h>
    #include <wchar.h> // Header file containing wprintf function
    // Driver code
    int main()
    {
        wint_t x = 5;
        wchar_t name[] = L"GEEKS";
        wprintf(L"x = %d \n", x);
        wprintf(L"HELLO %ls \n", name);
        return 0;
    }
    ```

    输出:

    ```cpp
    x = 5 
    HELLO GEEKS

    ```

2.  **wscanf() :** The wscanf() function reads the data from stdin and stores the values into the respective variables. The additional arguments should point to already allocated objects of the type specified by their corresponding format specifier within the format string.

    **语法:**

    ```cpp
    int wscanf (const wchar_t* format, ...);
    ```

    **参数:**

    *   **格式:**指向空终止字符串的指针，该字符串指定如何读取输入。它由以%开头的格式说明符组成。请注意，所有格式说明符的含义与 scanf 相同；因此，%lc 应该用于读取宽字符(而不是%c)，而%ls 应该用于宽字符串(而不是%s)。
    *   **……:**接收数据的其他附加参数。它们按照格式说明符的顺序出现。这些参数的数量至少应该与格式说明符存储的值的数量一样多。函数会忽略其他参数。
    *   **返回值:**wscanf()函数返回成功赋值的接收参数个数。我们可以计算并匹配预期的项目数，也可以由于匹配失败、出现读取错误或到达文件末尾导致错误而减少。
        如果在分配第一个接收参数之前失败，则返回 EOF。

    ```cpp
    // Program to show the wprintf () function.
    #include <stdio.h>
    #include <wchar.h> // Header file containing wscanf() function
    int main()
    {
        wchar_t str[80];
        int i;

        wscanf(L"%ls", str);
        wscanf(L"%d", &i);
        wprintf(L"I am a %ls of CSE in %d year.\n", str, i);
        return 0;
    }
    ```

    输入:

    ```cpp
    GEEK
    2

    ```

    输出:

    ```cpp
    I am a GEEK of CSE in 2 year.

    ```