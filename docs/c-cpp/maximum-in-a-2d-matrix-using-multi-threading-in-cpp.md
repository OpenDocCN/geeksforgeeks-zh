# 在 C++ 中使用多线程的 2D 矩阵中的最大值

> 原文:[https://www . geeksforgeeks . org/max-in-a-2d-matrix-use-多线程 in-cpp/](https://www.geeksforgeeks.org/maximum-in-a-2d-matrix-using-multi-threading-in-cpp/)

给定一个二维矩阵，使用多线程找到具有最大值的元素。
先决条件:[多线程](https://www.geeksforgeeks.org/multithreading-c-2/)

示例:

```cpp
Input : {{1, 5, 3, 6},
         {22, 10, 4, 34},
         {4, 45, 67, 3},  
         {69, 3, 23, 3}}
Output :69

Input :{{1, 2, 3}
        {2, 4, 5}}
Output :5

```

![](img/6cc474b3011f8ebf53d129646daaf358.png)

一个矩阵可以有很大的尺寸，所以当需要遍历它时，会花费很多时间。当在矩阵中寻找最大元素时，矩阵的每个元素都要遍历，这将花费更多的时间。因此，使用多线程可以避免遍历矩阵所需的时间。

```cpp
// CPP code to find max in 2d
// array using multi-threading
#include <bits/stdc++.h>
using namespace std;

// declaring two thread_id variable
pthread_t thread[2];

// structure for passing arguments
typedef struct dim
{
    int s, e;
}dim;

// matrix of 4X4
int mat1[][4] = {{1, 5, 3, 6}, {22, 80, 4, 34},
            {4, 45, 67, 3}, {99, 3, 23, 3}};
int maxf[2];

// function that find max from a given array
void *max(void *size)
{
    int i, j, max;
    dim *b = (dim *)size;
    max = mat1[b -> s][0];

    // finding max
    for(i = b -> s; i < b -> e; i++)
    {
        for(j = 0; j < 4; j++)
        {
            if(max < mat1[i][j])
                max = mat1[i][j];
        }
    }

    // storing max from first half of
    // 2-d array into 0th index
    if(b -> s == 0)
        maxf[0] = max;

    // storing max from second half of
    // 2-d array into 1st index
    else
    maxf[1] = max;
}

// driver function
int main()
{
    int i, j;
    dim *a, *b;
    a = (dim *)malloc(sizeof(dim));
    b = (dim *)malloc(sizeof(dim));

    // creating thread1
    a -> s = 0; a -> e = 4/2;
    pthread_create(&thread[0], NULL,
                &max, (void *)a);

    b -> s = 4/2; b -> e = 4;

    // creating thr ead 2
    pthread_create(&thread[1], NULL,
                &max, (void *)b);

    // waiting until the complition of threads
    pthread_join(thread[0], NULL);
    pthread_join(thread[1], NULL);

    // printing max
    if(maxf[0] > maxf[1])
    cout << maxf[0] << endl;
    else
    cout<< maxf[1] << endl;

    return 0;
}
```

输出: