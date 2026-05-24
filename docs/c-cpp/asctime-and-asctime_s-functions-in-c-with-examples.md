# asctime()和 asctime_s()在 C 中的函数，示例

> 原文:[https://www . geeksforgeeks . org/as time-and-as time _ s-functions-in-c-with-examples/](https://www.geeksforgeeks.org/asctime-and-asctime_s-functions-in-c-with-examples/)

**<u>asctime()函数:</u>**
**ASC time()**函数在 [**time.h 头文件**](https://www.geeksforgeeks.org/time-h-header-file-in-c-with-examples/) 中定义。该函数返回包含存储在指向 **struct tm** 类型的结构中的信息的字符串指针。该函数用于返回系统定义的当地时间。
**语法:**

```cpp
char *asctime(const struct tm* tm_ptr);
```

0 **参数:**该函数接受单个参数 **time_ptr** ，即指向要转换的 tm 对象的指针。
**返回类型:**该功能以“ **Www Mmm dd hh:mm:ss yyyy** 的形式返回**日历时间**，其中:

*   **Www** :用三个字母缩写表示一天(周一、周二、周三.., )
*   **嗯**:用三个字母缩写表示月份(一月、二月、三月.., )
*   **dd** :两位数表示日期(01、02、10、21、31.., )
*   **hh** :代表小时(11，12，13，22…，)
*   **mm** :表示分钟(10，11，12，45…，)
*   **ss** :表示秒(10，20，30…，)
*   **yyyy** :用四位数表示年份(2000、2001、2019、2020……，)

下面的程序演示了 C 语言中的 asctime()函数:

## C

```cpp
// C program to demonstrate
// the asctime() function

#include <stdio.h>
#include <time.h>

int main()
{
    struct tm* ptr;
    time_t lt;
    lt = time(NULL);
    ptr = localtime(<);

    // using the asctime() function
    printf("%s", asctime(ptr));

    return 0;
}
```

**Output:** 

```cpp
Wed Aug 14 04:21:25 2019
```