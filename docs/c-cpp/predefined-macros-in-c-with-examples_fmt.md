# 预定义宏在 C 语言中的示例

> 原文：[https://www.geeksforgeeks.org/predefined-macros-in-c-with-examples/](https://www.geeksforgeeks.org/predefined-macros-in-c-with-examples/)

根据 C89 标准，C 编程语言具有以下预定义的宏：

## `__LINE__` 宏

`__LINE__` 宏包含编译中程序的当前行号。它给出了调用它的行号。它用于生成日志语句、错误消息、抛出异常和调试代码。每当编译器在编译中发现错误时，它首先使用 `__LINE__` 生成发生错误的行号，并打印错误消息和行号，以便用户可以轻松修复该错误。

```cpp
#include <stdio.h>
int main()
{
    printf("Line number is: %d\n",
           __LINE__);
    return 0;
}
```

**输出：**

## `__FILE__` 宏

`__FILE__` 宏保存计算机中当前正在执行的程序的文件名。它还用于调试、生成错误报告和日志消息。

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

**输出：**

> 这个程序的文件名是：/usr/share/IDE_PROGRAMES/C/other/703ad0b087FBD7d18CDE5ea81f148f36/703ad0b087FBD7d18CDE5ea81f148f36.c

## `__DATE__` 宏

`__DATE__` 宏给出本程序源代码转换为目标代码的日期。简单地说，它返回程序编译的日期。日期格式为 *mmm dd yyyy*。*mmm* 是缩写的月份名称。

```cpp
#include <stdio.h>
int main()
{
    printf("Program Compilation Date: %s\n",
           __DATE__);
    return 0;
}
```

**输出：**

```cpp
Program Compilation Date: Dec 26 2019
```

## `__TIME__` 宏

`__TIME__` 宏给出程序编译的时间。时间格式为 *hh:mm:ss*。

```cpp
#include <stdio.h>
int main()
{
    printf("Time of compilation is: %s\n",
           __TIME__);
    return 0;
}
```

**输出：**

```cpp
Time of compilation is: 13:17:20
```

## `__STDC__` 宏

`__STDC__` 宏用于确认编译器标准。一般为值 1，表示编译器符合 ISO 标准 C。

```cpp
#include <stdio.h>
int main()
{
    printf("Compiler Standard Number: %d\n",
           __STDC__);
    return 0;
}
```

**输出：**

```cpp
Compiler Standard Number: 1
```

## `__STDC_HOSTED__` 宏

如果编译器的目标是托管环境，则该宏的值为 1。托管环境是第三方保存编译数据并在自己的计算机上运行程序的设施。通常，该值设置为 1。

```cpp
#include <stdio.h>
int main()
{
    printf("STDC_HOSTED Number: %d\n",
           __STDC_HOSTED__);
    return 0;
}
```

**输出：**

## `__STDC_VERSION__` 宏

这个宏保存 C 标准的版本号，形式为 *yyyymmL*，其中 *yyyy* 和 *mm* 是标准版本的年份和月份。这表示编译器符合哪个版本的 C 标准。

```cpp
Values hold by __STDC_VERSION__
```

*   值 199409L 表示 1994 年修订的 C89 标准。这是当前的默认标准。
*   值 199901L 表示 C99 标准。
*   值 201112L 表示 C 标准的 2011 修订版。

当用户需要使用 C89 标准中的函数或头文件时，这些标准值会发生变化，C99 标准中删除了该功能或头文件。编译器改变其执行标准并运行输出。

查看[这篇](https://www.geeksforgeeks.org/asctime-and-asctime_s-functions-in-c-with-examples/)文章，它将标准更改为运行 C89 标准中声明的 `asctime_s()` 函数。

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

### C99 标准中的预定义宏

## `__cplusplus` 宏

`__cplusplus` 宏是在使用 C++ 编译器时定义的。它用于测试头文件是由 C 编译器还是 C++ 编译器编译的。这个宏给出的值类似于 `__STDC_VERSION__`，因为它扩展到了一个版本号。

```cpp
Values hold by __cplusplus
```

*   199711L 适用于 1998 年 C++ 标准。
*   201103L 适用于 2011 年 C++ 标准。
*   201402L 适用于 2014 年 C++ 标准。
*   201703L 适用于 2017 年 C++ 标准。

## `__OBJC__` 宏

`__OBJC__` 宏的值为 1，如果 Objective-C 编译器正在使用。`__OBJC__` 用于测试头文件是由 C 编译器还是 Objective-C 编译器编译的。

**参考文献：**