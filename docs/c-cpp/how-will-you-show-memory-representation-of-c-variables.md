# 你将如何展示 C 变量的记忆表征？

> 原文:[https://www . geeksforgeeks . org/你将如何显示 c 变量的内存表示/](https://www.geeksforgeeks.org/how-will-you-show-memory-representation-of-c-variables/)

编写一个 C 程序来显示 C 变量的内存表示，如 int、float、pointer 等。

**算法:**
获取变量的地址和大小。将地址类型转换为字符指针。现在循环变量的大小，并在类型化指针处打印值。

**程序:**

```cpp
#include <stdio.h>
typedef unsigned char *byte_pointer;

/*show bytes takes byte pointer as an argument
  and prints memory contents from byte_pointer
  to byte_pointer + len */
void show_bytes(byte_pointer start, int len) 
{
     int i;
     for (i = 0; i < len; i++)
           printf(" %.2x", start[i]);
     printf("\n");
}

void show_int(int x)
{
     show_bytes((byte_pointer) &x, sizeof(int));
}

void show_float(float x) 
{
     show_bytes((byte_pointer) &x, sizeof(float));
}

void show_pointer(void *x) 
{
     show_bytes((byte_pointer) &x, sizeof(void *));
}

/* Drover program to test above functions */
int main()
{
    int i = 1;
    float f = 1.0;
    int *p = &i;
    show_float(f);
    show_int(i);
    show_pointer(p);
    show_int(i);
    getchar();
    return 0;
}
```