# c++ 中的时钟头文件

> 原文:[https://www.geeksforgeeks.org/clocale-header-file-in-c/](https://www.geeksforgeeks.org/clocale-header-file-in-c/)

**clocal**:这个头文件包含一组函数的声明和国际化支持任务的类型。它支持日期格式或国家特定的货币符号。
例如，日期/时间格式、货币格式等等。

**时钟标题**中的方法:

1.  **localeconv()**: This function returns an object which represents numeric and monetary formatting rules of the current C locale. Its corresponding header file is **.** The “c” locale is the minimal locale. It is a locale which has the same settings across all the compilers, so the result is predictable anyway. By default used on all C programs.

    **原型**

    ```cpp
    lconv* localeconv();

    ```

    **参数:**该方法没有参数。

    **返回值**:该函数返回一个指向静态对象的指针，该静态对象包含当前 C 语言环境的数字和货币格式规则。

    **程序:**

    ```cpp
    #include <iostream>
    #include <locale.h>
    using namespace std;

    int main()
    {
        setlocale(LC_MONETARY, "en_US.utf8");
        struct lconv* lc = localeconv();
        printf("%s ", lc->currency_symbol);
        return 0;
    }
    ```

    **Output:**

    ```cpp
    $

    ```

2.  **setlocale()**: The setlocale() function installs the specified system locale. Moreover, it sets the locale information for the current C program. It can also be used to query the current C locale. It has some parameters namely,
    *   选择所有的 C 语言环境
    *   选择数字格式类别
    *   LC_MONETARY ->货币格式类别
    *   LC_CTYPE ->字符分类类别
    *   LC_TIME ->时间格式类别

    **原型**:

    ```cpp
    int setlocale(int category, const char* locale);

    ```

    **返回值**:应用更改后返回一个标识 C 语言环境的字符串指针。否则，它将返回空指针。

    **程序:**

    ```cpp
    #include <clocale>
    #include <iostream>
    using namespace std;

    int main()
    {
        char* s;
        setlocale(LC_ALL, "en_UA.utf8");
        s = setlocale(LC_ALL, NULL);
        cout << s << "\n";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    C

    ```