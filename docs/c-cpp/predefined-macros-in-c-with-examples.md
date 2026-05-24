# 预定义宏在 C 语言中的示例

> 原文:[https://www . geesforgeks . org/predefined-macros-in-c-with-examples/](https://www.geeksforgeeks.org/predefined-macros-in-c-with-examples/)

根据 C89 标准，C 编程语言具有以下预定义的宏:

1.  **_ _ LINE _ _ Macro**:_ _ LINE _ _ Macro 包含编译中程序的当前行号。它给出了调用它的行号。它用于生成日志语句、错误消息、抛出异常和调试代码。每当编译器在编译中发现错误时，它首先使用 __LINE__ 生成发生错误的行号，并打印错误消息和行号，以便用户可以轻松修复该错误。T5】CT7

    ```cpp
    #include <stdio.h>
    int main()
    {
        printf("Line number is: %d\n",
               __LINE__);
        return 0;
    }
    ```

    T8T10**输出:**T1
2.  **_ _ FILE _ _ Macro**:_ _ FILE _ _ Macro 保存计算机中当前正在执行的程序的文件名。它还用于调试、生成错误报告和日志消息。

    ## C

    ```cpp
    #include <stdio.h>
    int main()
    {
        printf("File name of this"
               " program is: %s\n",
               __FILE__);
        return 0;
    }
    ```

    **输出:**

    > 这个程序的文件名是://usr/share/IDE _ PROGRAMES/C/other/703 ad 0 b 087 FBD 7d 18 CDE 5 ea 81 f 148 f 36/703 ad 0 b 087 FBD 7d 18 CDE 5 ea 81 f 148 f 36。C

3.  **_ _ DATE _ _ Macro**:_ _ DATE _ _ Macro 给出本程序源代码转换为目标代码的日期。简单地说，它返回程序编译的日期。日期格式为*年月日*。mmm 是缩写的月份名称。

    ## C

    ```cpp
    #include <stdio.h>
    int main()
    {
        printf("Program Compilation Date: %s\n",
               __DATE__);
        return 0;
    }
    ```

    **输出:**

    ```cpp
    Program Compilation Date: Dec 26 2019

    ```

4.  **_ _ TIME _ _ Macro**:_ _ DATE _ _ Macro 给出程序编译的时间。时间格式为*小时:分钟:秒*。

    ## C

    ```cpp
    #include <stdio.h>
    int main()
    {
        printf("Time of compilation is: %s\n",
               __TIME__);
        return 0;
    }
    ```

    **输出:**

    ```cpp
    Time of compilation is: 13:17:20

    ```

5.  **__STDC__ 宏** : __STDC__ 宏用于确认编译器标准。一般为值 1，表示编译器符合 ISO 标准 C .

    ## C

    ```cpp
    #include <stdio.h>
    int main()
    {
        printf("Compiler Standard Number: %d\n",
               __STDC__);
        return 0;
    }
    ```

    **输出:**

    ```cpp
    Compiler Standard Number: 1

    ```

6.  **_ _ STDC _ _ 托管宏**:如果编译器的目标是托管环境，则该宏的值为 1。托管环境是第三方保存编译数据并在自己的计算机上运行程序的设施。通常，该值设置为 1。T5】CT7

    ```cpp
    #include <stdio.h>
    int main()
    {
        printf("STDC_HOSTDED Number: %d\n",
               __STDC_HOSTED__);
        return 0;
    }
    ```

    T8T10**输出:**T1
7.  **__STDC_VERSION__**: This macro holds the C Standard’s version number in the form *yyyymmL* where yyyy and mm are the year and month of the Standard version. This signifies which version of the C Standard the compiler conforms to.

    ```cpp
    Values hold by __STDC_VERSION__
    ```

    *   值 199409L 表示 1994 年修订的 C89 标准。这是当前的默认标准。
    *   值 199901 表示 C99 标准
    *   值 201112L 表示 C 标准的 2011 修订版

    当用户需要使用 C89 标准中的函数或头文件时，这些标准值会发生变化，C99 标准中删除了该功能或头文件。编译器改变其执行标准并运行输出。

    查看[这篇](https://www.geeksforgeeks.org/asctime-and-asctime_s-functions-in-c-with-examples/)文章，它将标准更改为运行 C89 标准中声明的 asctime _ s()函数。

    ## C

    ```cpp
    #include <stdio.h>
    int main()
    {
        printf("Compiler Standard "
               "VERSION Number: %ld\n",
               __STDC_VERSION__);
        return 0;
    }
    ```

    **Output:**

    ```cpp
    Compiler Standard VERSION Number: 201112

    ```

    ### C99 标准中的预定义宏:

8.  **__cplusplus** : __cplusplus 宏是在使用 C++ 编译器时定义的。它用于测试头文件是由 C 编译器还是 C++ 编译器编译的。这个宏给出的值类似于 __ STDC _ 版本 _ _，因为它扩展到了一个版本号。

    ```cpp
    Values hold by __cplusplus
    ```

    *   199711L 适用于 1998 年 C++ 标准
    *   2011 年 C++ 标准的 201103L
    *   2014 C++ 标准的 201402L
    *   201703L 适用于 2017 年 C++ 标准
9.  **_ _ OBJC _ _ Macro:**:_ _ OBJC _ _ Macro 的值为 1，如果 Objective-C 编译器正在使用。__OBJC__ 用于测试头文件是由 C 编译器还是 Objective-C 编译器编译的。

**参考文献:**