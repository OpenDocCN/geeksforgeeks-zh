# 多线程线性搜索

> 原文:[https://www . geesforgeks . org/linear-search-use-multi-threading/](https://www.geeksforgeeks.org/linear-search-using-multi-threading/)

给定一个大的整数文件，使用多线程搜索其中的特定元素。

示例:

```cpp
Input : 1, 5, 7, 10, 12, 14, 15, 18, 20, 
        22, 25, 27, 30, 64, 110, 220
Output :if key = 20
Key element found

Input :1, 5, 7, 10, 12, 14, 15, 18, 20, 
       22, 25, 27, 30, 64, 110, 220
Output :if key = 202
Key not present

```

**先决条件:** [多线程](https://www.geeksforgeeks.org/multithreading-in-cpp/)

**方法:**
首先创建 n 个线程。然后，将数组分成四个部分，每个线程一个部分，并使用多线程对各个部分进行线性搜索，并检查关键元素是否存在。

```cpp
Command : g++ -pthread linear_thread.cpp

```

## C++

```cpp
// CPP code to search for element in a
// very large file using Multithreading
#include <iostream>
#include <pthread.h>
using namespace std;

// Max size of array
#define max 16

// Max number of threads to create
#define thread_max 4

int a[max] = { 1, 5, 7, 10, 12, 14, 15,
               18, 20, 22, 25, 27, 30,
               64, 110, 220 };
int key = 202;

// Flag to indicate if key is found in a[]
// or not.
int f = 0;

int current_thread = 0;

// Linear search function which will
// run for all the threads
void* ThreadSearch(void* args)
{
    int num = current_thread++ ;

    for (int i = num * (max / 4); 
         i < ((num + 1) * (max / 4)); i++) 
    {
        if (a[i] == key)
            f = 1;
    }
}

// Driver Code
int main()
{
    pthread_t thread[thread_max];

    for (int i = 0; i < thread_max; i++) {
        pthread_create(&thread[i], NULL, 
                      ThreadSearch, (void*)NULL);
    }

    for (int i = 0; i < thread_max; i++) {
        pthread_join(thread[i], NULL);
    }

    if (f == 1)
        cout << "Key element found" << endl;
    else
        cout << "Key not present" << endl;
    return 0;
}
```

Output:

```cpp
Key not present

```

**练习:**以上代码将数组划分为四个子数组。将其扩展为一个决定划分(或线程)数量的参数。