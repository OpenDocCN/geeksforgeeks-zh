# C |指针基础|第 15 题

> 原文:[https://www.geeksforgeeks.org/c-pointer-basics-question-15/](https://www.geeksforgeeks.org/c-pointer-basics-question-15/)

```cpp
#include<stdio.h>

void swap (char *x, char *y)
{
    char *t = x;
    x = y;
    y = t;
}

int main()
{
    char *x = "geeksquiz";
    char *y = "geeksforgeeks";
    char *t;
    swap(x, y);
    printf("(%s, %s)", x, y);
    t = x;
    x = y;
    y = t;
    printf("\n(%s, %s)", x, y);
    return 0;
}
```

**(甲)**

```cpp
(geeksquiz, geeksforgeeks)
(geeksforgeeks, geeksquiz)
```

**(B)**

```cpp
(geeksforgeeks, geeksquiz)
(geeksquiz, geeksforgeeks)
```

**(C)**

```cpp
(geeksquiz, geeksforgeeks)
(geeksquiz, geeksforgeeks)
```

**(D)**

```cpp
(geeksforgeeks, geeksquiz)
(geeksforgeeks, geeksquiz)
```

**答案:** **(A)**

**说明:**参见 [C 功能对换字符串](https://www.geeksforgeeks.org/swap-strings-in-c/)

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)