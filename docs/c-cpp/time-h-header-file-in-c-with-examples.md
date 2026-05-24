# 带示例的 C 中的 time.h 头文件

> 原文:[https://www . geesforgeks . org/time-h-header-file-in-c-with-examples/](https://www.geeksforgeeks.org/time-h-header-file-in-c-with-examples/)

**time.h** 头文件包含获取和操作日期和时间信息的函数的定义。

*   它描述了三种与时间相关的数据类型。
    1.  **clock_t** : clock_t 将日期表示为整数，是日历时间的一部分。

    2.  **time_t** : time_t 表示时钟时间为整数，是日历时间的一部分。

    3.  **struct tm** : struct tm 保存日期和时间，包含:

## C

```cpp
struct tm {
    // seconds,  range 0 to 59
    int tm_sec;

    // minutes, range 0 to 59
    int tm_min;

    // hours, range 0 to 23
    int tm_hour;

    // day of the month, range 1 to 31
    int tm_mday;

    // month, range 0 to 11
    int tm_mon;

    // The number of years since 1900
    int tm_year;

    // day of the week, range 0 to 6
    int tm_wday;

    // day in the year, range 0 to 365
    int tm_yday;

    // daylight saving time
    int tm_isdst;
}
```

*   它还包含**CHOCKS _ PER _ SEC**宏，该宏保存系统时钟每秒滴答的次数。
*   **预定义功能**及时

<figure class="table">

| S.No | 函数名 | 说明 |
| --- | --- | --- |
| 1. | asctime（） | 该函数以
日月日期小时:分钟:秒年的格式返回日期和时间。
例如:2019 年 7 月 27 日星期六 11:26:03。
asctime()函数通过将 struct tm 变量作为参数返回一个字符串。 |
| 2. | 时钟() | 该函数返回程序消耗的处理器时间 |
| 3. | ctime() | 此函数以
日月小时:分钟:秒年
的格式返回日期和时间例如:2019 年 7 月 27 日星期六 11:26:03
时间根据日历时间返回的指针打印 |
| 4. | [差异时间 （）](https://www.geeksforgeeks.org/difftime-c-library-function/) | 该函数返回提供的时间之间的差值。 |
| 5. | [gmtime（）](https://www.geeksforgeeks.org/gmtime-function-in-c-c/) | 此功能打印世界协调时时间和日期。
gmtime()和 asctime()的格式相同 |
| 6. | mktime（） | 此函数使用 struct tm 返回等效日历时间。 |
| 7. | 时间() | 此函数使用数据类型 time_t 返回等效日历时间。 |
| 8. | strftime（） | 这个函数有助于格式化由使用不同格式说明符的其他时间函数返回的字符串 |

</figure>

*   **示例:**
    1.  程序打印系统的日期和时间。

## C

```cpp
#include <stdio.h>
#include <time.h>
int main(void)
{
    struct tm* ptr;
    time_t t;
    t = time(NULL);
    ptr = localtime(&t);
    printf("%s", asctime(ptr));
    return 0;
}
```

**Output:** 

```cpp
Tue Aug  6 09:00:29 2019
```

2.打印系统协调世界时的程序。

## C

```cpp
#include <stdio.h>
#include <time.h>
int main(void)
{
    struct tm* ptr;
    time_t t;
    t = time(NULL);
    ptr = gmtime(&t);
    printf("%s", asctime(ptr));
    return 0;
}
```

**Output:** 

```cpp
Tue Aug  6 09:00:31 2019
```

3.计算两个数相加时间的程序。
**注意:**如果用户慢慢输入，那么这个时间也加起来就是总执行时间。

## C

```cpp
#include <stdio.h>
#include <time.h>
int main(void)
{
    time_t start, end;
    start = time(NULL);
    int a, b;
    scanf("%d %d", &a, &b);
    printf("Sum of %d and %d is %d\n",
           a, b, a + b);
    end = time(NULL);
    printf("Time taken to print sum is %.2f seconds",
           difftime(end, start));
}
```

**Output:** 

```cpp
Sum of 4196144 and 0 is 4196144
Time taken to print sum is 0.00 seconds
```

4.寻找时钟滴答声的程序。

## C

```cpp
#include <math.h>
#include <stdio.h>
#include <time.h>

int frequency_of_primes(int n)
{
    // This function checks the number of
    // primes less than the given parameter
    int i, j;
    int freq = n - 1;
    for (i = 2; i <= n; ++ i)
        for (j = sqrt(i); j > 1; --j)
            if (i % j == 0) {
                --freq;
                break;
            }
    return freq;
}

int main()
{
    clock_t t;
    int f;
    t = clock();
    f = frequency_of_primes(9999);
    printf("The number of primes lower"
           " than 10, 000 is: %d\n",
           f);
    t = clock() - t;
    printf("No. of clicks %ld clicks (%f seconds).\n",
           t, ((float)t) / CLOCKS_PER_SEC);
    return 0;
}
```

**Output:** 

```cpp
The number of primes lower than 10, 000 is: 1229
No. of clicks 2837 clicks (0.002837 seconds).
```

5.将时间打印为 asctime()文件返回的小时:分钟的程序。

## C

```cpp
#include <stdio.h>
#include <time.h>
int main()
{
    time_t rawtime;
    struct tm* timeinfo;

    // Used to store the time
    // returned by localetime() function
    char buffer[80];

    time(&rawtime);
    timeinfo = localtime(&rawtime);
    strftime(buffer, 80,
             "Time is %I:%M%p.",
             timeinfo);

    // strftime() function stores the
    // current time as Hours : Minutes
    //%I %M and %p-> format specifier
    // of Hours minutes and am/pm respectively*/

    // prints the formatted time
    puts(buffer);

    return 0;
}
```

**Output:** 

```cpp
Time is 09:00AM.
```