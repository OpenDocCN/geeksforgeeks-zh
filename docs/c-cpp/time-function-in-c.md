# 时间()功能在 C

> 原文:[https://www.geeksforgeeks.org/time-function-in-c/](https://www.geeksforgeeks.org/time-function-in-c/)

time()函数在 time . h(c++ 中的 ctime)头文件中定义。此函数以秒为单位返回自 1970 年 1 月 1 日 00:00:00 UTC 以来的时间(Unix 时间戳)。如果 second 不是空指针，返回值也存储在 second 指向的对象中。

**语法:**

```cpp
time_t time( time_t *second )
```

**参数:**此功能接受单参数*秒*。该参数用于设置存储时间的 time_t 对象。
**返回值:**该函数以 time_t 类型的对象返回当前日历时间

**程序 1:**

## C

```cpp
// C program to demonstrate
// example of time() function.
#include <stdio.h>
#include <time.h>

int main ()
{
    time_t seconds;

    seconds = time(NULL);
    printf("Seconds since January 1, 1970 = %ld\n", seconds);

    return(0);
}
```

**Output:** 

```cpp
Seconds since January 1, 1970 = 1538123990
```

**例 2:**

## C

```cpp
// C program to demonstrate
// example of time() function.

#include <stdio.h>
#include <time.h>

int main()
{
    time_t seconds;

     // Stores time seconds
    time(&seconds);
    printf("Seconds since January 1, 1970 = %ld\n", seconds);

    return 0;
}
```

**Output:** 

```cpp
Seconds since January 1, 1970 = 1538123990
```