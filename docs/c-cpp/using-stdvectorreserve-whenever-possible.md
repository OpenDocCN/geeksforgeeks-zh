# 使用标准::矢量::尽可能保留

> 原文:[https://www . geesforgeks . org/using-stdvectoreserve-尽可能/](https://www.geeksforgeeks.org/using-stdvectorreserve-whenever-possible/)

在 C++ 中，向量是动态数组。与数组不同，它们没有固定的大小。它们可以根据需要生长或收缩。向量在连续位置的块中被分配给存储器。当为向量分配的内存不足以存储新元素时，会为向量分配一个新的内存块，并将所有元素从旧位置复制到新位置。这种元素的重新分配有助于向量在需要时增长。然而，这是一个昂贵的操作，并且这一步所涉及的时间复杂度是线性的。

**std::vector** 类提供了一个有用的函数 **reserve** ，帮助用户指定向量的最小大小。它表示创建向量时，它可以至少存储指定元素的数量，而不必重新分配内存。

**std::vector::reserve**

```cpp
void reserve(size_type n)
Return Type: none
Arguments: n which denotes the no of elements to be stored in vector

Requests that vector is large enough to store n elements in the least. 
If the current vector capacity is less than n, then reallocation will 
take place. In other cases, reallocation will not happen. Function does
not modify existing elements in the vector

```

每个矢量对象有两个参数——大小和容量。大小表示当前存储在向量中的元素数量，而容量是向量无需重新分配即可存储的最大元素数量。显然容量> =大小。当向量空间不足以存储新元素时，即当大小变得大于容量时，运行时库将从堆中请求新的内存，一旦内存被分配，它将把向量中的所有元素从它们的旧地址复制到新分配的内存地址。对函数保留的调用修改了向量的容量参数，因此向量请求足够的内存来存储指定数量的元素。

这里有一个程序来演示使用保留函数可以获得的性能改进。在这个程序中，我们用大量元素填充两个向量，并计算执行这个步骤所花费的时间。对于第一个向量，我们不指定容量，而对于第二个向量，我们使用 reserve()指定容量。

```cpp
// CPP program to demonstrate use of 
// std::vector::reserve 
#include <chrono>
#include <iostream>
#include <vector>

using std::vector;
using std::cout;
using namespace std::chrono;

int main()
{
    // No of charactes
    int N = (int)1e6;

    vector<int> v1, v2;

    // Reserve space in v2
    v2.reserve(N);

    // Start filling up elements in v1
    // To measure execution time in C++, refer below
    // https://www.geeksforgeeks.org/measure-execution-time-function-cpp/

    auto start = high_resolution_clock::now();
    for (int i = 0; i < N; ++ i)
        v1.push_back(i);
    auto stop = high_resolution_clock::now();
    auto duration = duration_cast<microseconds>(stop - start);

    cout << "Method I took " << duration.count() << " microseconds\n";

    // Start filling up elements in v2
    start = high_resolution_clock::now();
    for (int i = 0; i < N; ++ i)
        v2.push_back(i);
    stop = high_resolution_clock::now();
    duration = duration_cast<microseconds>(stop - start);

    cout << "Method II took " << duration.count() 
         << " microseconds \n";

    return 0;
}
```

输出:(取决于机器)

```cpp
Method I took 18699 microseconds
Method II took 16276 microseconds 

```

**注意:**
保证预先预留空间比不指定向量大小就尝试插入元素花费的时间少。此外，它给代码增加了语义效用，我们至少知道向量会有多大。