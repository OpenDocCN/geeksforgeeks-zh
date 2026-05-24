# 使用 pthreads 的超大型数组中的最大元素

> 原文:[https://www . geesforgeks . org/maximum-element-large-array-using-pthreads/](https://www.geeksforgeeks.org/maximum-element-large-array-using-pthreads/)

给定一个非常大的整数数组，使用多线程在数组中找到最大值。

**示例:**

```cpp
Input :  1, 5, 7, 10, 12, 14, 15, 18, 20, 
         22, 25, 27, 30, 64, 110, 220
Output :Maximum Element is : 220

Input :  10, 50, 70, 100, 120, 140, 150, 180, 
         200, 220, 250, 270, 300, 640, 110, 220
Output : Maximum Element is : 640

```

**先决条件:** [多线程](https://www.geeksforgeeks.org/multithreading-c-2/)

**注意:**在大小为 MB/GB 的大文件中有用。

**如何运行:**
只能在 linux 环境下运行。
命令:

```cpp
>> gcc -pthread maximum.c 
>> ./a.out

```

```cpp
// C++ code to find maximum of an array using Multithreading
#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>

// Size of array
#define max 16

// Max number of thread
#define Th_max 4

// Array
int a[max] = { 1, 5, 7, 10, 12, 14, 15, 18, 20,
               22, 25, 27, 300, 64, 110, 220 };

// Array to store max of threads
int max_num[Th_max] = { 0 };
int thread_no = 0;

// Function to find maximum
void maximum(void* arg)
{
    int i, num = thread_no++ ;
    int maxs = 0;

    for (i = num * (max / 4); i < (num + 1) * (max / 4); i++) {
        if (a[i] > maxs)
            maxs = a[i];
    }

    max_num[num] = maxs;
}

// Driver code
int main()
{
    int maxs = 0;
    int i;
    pthread_t threads[Th_max];

    // creating 4 threads
    for (i = 0; i < Th_max; i++)
        pthread_create(&threads[i], NULL,
                       maximum, (void*)NULL);

    // joining 4 threads i.e. waiting for
    // all 4 threads to complete
    for (i = 0; i < Th_max; i++)
        pthread_join(threads[i], NULL);

    // Finding max element in an array
    // by individual threads
    for (i = 0; i < Th_max; i++) {
        if (max_num[i] > maxs)
            maxs = max_num[i];
    }

    printf("Maximum Element is : %d", maxs);

    return 0;
}
```

输出:

```cpp
Maximum Element is : 300

```