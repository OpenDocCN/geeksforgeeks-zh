# wctob()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/wctob-function-in-c/](https://www.geeksforgeeks.org/wctob-function-in-c/)

C++ 中的 wctob()函数有助于将宽字符 *wc* 转换为单字节，如果其 if 在初始移位状态下的多字节字符等效为单字节。由于该函数使用单字节编码，因此用于 ASCII 字符集的字符。

**语法:**

```cpp
int wctob (wint_t wc);

```

**参数:**上述函数接受单个参数，如下所述:

*   **wc:** This is the only parameter accepted by the wctob() function, it is the wide character needed to be narrowed/converted .

    **返回类型:**如果宽字符 wc 对应于初始状态下长度为单字节的多字节字符，则函数返回宽字符 WC 的单字节表示。否则，它将返回 EOF(文件结束)。

    以下程序说明了上述功能:

    **程序 1:**

    ```cpp
    // Program illustrating
    // wctob() function
    #include <bits/stdc++.h>

    // function implementing the wctob() function
    int fun()
    {

        int i, num;
        const wchar_t wc[] = L"priya lal";

        num = 0;
        for (i = 0; i < wcslen(wc); ++ i)
            if (wctob(wc[i]) != EOF)
                ++ num;

        // prints the numbers of characters
        // needed to be translated
        wprintf(L"wc has %d characters to be translated"
                "to single-byte characters.",
                num);
    }

    // Driver Program
    int main()
    {
        fun();
        return 0;
    }
    ```

    **Output:**

    ```cpp
    wc has 9 characters to be translatedto single-byte characters.

    ```

    **程序 2 :**

    ```cpp
    // C++ program illustrating the wctob() function
    #include <bits/stdc++.h>

    // function implementing the wctob() function
    void fun(wchar_t wc)
    {

        int cn = wctob(wc);
        if (cn != EOF)

            printf("%#x translated to %#x\n", wc, cn);

        else

            printf("%#x could not be translated\n", wc);
    }

    // Driver Program
    int main(void)
    {
        char* utf_locale_present
            = setlocale(LC_ALL, "th_TH.utf8");

        // prints the result of the function
        puts("In Thai UTF-8 locale:");
        fun(L'a');
        fun(L'?');
    }
    ```

    **Output:**

    ```cpp
    In Thai UTF-8 locale:
    0x61 translated to 0x61
    0x3f translated to 0x3f

    ```