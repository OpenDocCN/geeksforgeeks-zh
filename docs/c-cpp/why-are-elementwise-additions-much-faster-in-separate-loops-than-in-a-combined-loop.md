# 为什么元素加法在独立循环中比在组合循环中快得多？

> 原文:[https://www . geesforgeks . org/为什么元素式加法在单独循环中比在组合循环中快得多/](https://www.geeksforgeeks.org/why-are-elementwise-additions-much-faster-in-separate-loops-than-in-a-combined-loop/)

当添加 2 个以上的数组时，用于逐步添加元素的单独循环证明比在单个循环中添加元素具有更好的性能。

为了测试上述语句，两个代码块添加了 4 个数组元素，即带有 b 的数组 a 和带有 d 的数组 c。第一个代码块使用组合循环来添加它们，而第二个代码块使用两个不同的 for 循环。时钟在两个程序中都用于测量执行循环所花费的时间。

**使用组合循环**

```cpp
// C program to illustrate
// performance of loops
#include <bits/stdc++.h>
using namespace std;
int main()
{
    const int n = 100000;

    double* a1 = (double*)malloc(n * sizeof(double));
    double* b1 = (double*)malloc(n * sizeof(double));
    double* c1 = (double*)malloc(n * sizeof(double));
    double* d1 = (double*)malloc(n * sizeof(double));

    // Zero the data to prevent any chance of denormals.
    memset(a1, 0, n * sizeof(double));
    memset(b1, 0, n * sizeof(double));
    memset(c1, 0, n * sizeof(double));
    memset(d1, 0, n * sizeof(double));
    clock_t start = clock();

    int c = 0;
    while (c++ < 10000) {
        for (int j = 0; j < n; j++) {
            a1[j] += b1[j];
            c1[j] += d1[j];
        }
    }
    clock_t end = clock();
    cout << "seconds = " << (double)(end - start) / CLOCKS_PER_SEC << endl;

    return 0;
}
```

输出:

```cpp
seconds = 2.47865
```

**使用独立回路**

```cpp
// C program to illustrate
// performance of loops
#include <bits/stdc++.h>
using namespace std;
int main()
{
    const int n = 100000;

    double* a1 = (double*)malloc(n * sizeof(double));
    double* b1 = (double*)malloc(n * sizeof(double));
    double* c1 = (double*)malloc(n * sizeof(double));
    double* d1 = (double*)malloc(n * sizeof(double));

    // Zero the data to prevent any chance of denormals.
    memset(a1, 0, n * sizeof(double));
    memset(b1, 0, n * sizeof(double));
    memset(c1, 0, n * sizeof(double));
    memset(d1, 0, n * sizeof(double));
    clock_t start = clock();

    int c = 0;

    while (c++ < 10000) {

        for (int j = 0; j < n; j++) {
            a1[j] += b1[j];
        }
        for (int j = 0; j < n; j++) {
            c1[j] += d1[j];
        }
    }

    clock_t end = clock();
    cout << "seconds = " << (double)(end - start) / CLOCKS_PER_SEC << endl;

    // system("pause");
    return 0;
}
```

输出:

```cpp
seconds = 2.07937
```

注意:实际输出时间取决于所用的编译器

从上面的例子中我们可以看出，单独的循环比组合循环更快。原因是假设一个简单的后进先出缓存策略，单独的循环将首先导致 a 和 b 被加载到内存中，然后完全在内存中工作。当第二个循环开始时，c 和 d 将从磁盘加载到内存中并运行。因此，阵列被加载到存储器中一次。

而组合循环每次都会调出两个数组并调入另外两个数组。因此，与单独的循环相比，组合循环要慢得多，因为页入页出必须重复进行，在单独的循环中，数组被加载一次并进行处理。