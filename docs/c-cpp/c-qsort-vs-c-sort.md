# C qsort() vs C++ sort()

> 原文:[https://www.geeksforgeeks.org/c-qsort-vs-c-sort/](https://www.geeksforgeeks.org/c-qsort-vs-c-sort/)

标准 C 库提供了一个 qsort 函数，可以用来对数组进行排序。下面是 qsort()函数的原型。

```cpp
// Sort an array of any type. The parameters are, base
// address of array, size of array and pointer to
// comparator function
void qsort (void* base, size_t num, size_t size, 
            int (*comparator)(const void*, const void*));
```

它需要一个指向数组的指针、数组中元素的数量、每个元素的大小以及一个比较器函数。我们已经在这里详细讨论了 qsort 比较器。

C++ 标准库提供了一个类似的函数 sort()，它起源于 STL。我们已经在这里讨论了 C++ 排序。以下是 C++ sort()函数的原型。

```cpp
// To sort in default or ascending order.
template void sort(T first, T last);

// To sort according to the order specified
// by comp.
template <class t="" class="" compare="">void sort(T first, T last, Compare comp);</class> 
```

相等元素的顺序不能保证被保留。C++ 提供了 std::stable_sort，可用于保持顺序。

**比较 qsort 和 sort()**
**1。实现细节:**
顾名思义，qsort 函数使用 QuickSort 算法对给定数组进行排序，虽然 C 标准并不要求它实现 quicksort。

C++ 排序函数使用了一种混合算法 introsort。不同的实现使用不同的算法。例如，GNU 标准 C++ 库使用了一个 3 部分混合排序算法:首先执行 intro sort(intro sort 本身是快速排序和堆排序的混合)，然后对结果执行插入排序。

**2。复杂性:**
C 标准没有谈到其 qsort 的复杂性。新的 C++ 11 标准要求在最坏的情况下排序的复杂度为 O(Nlog(N))。C++ 的早期版本，如 C++ 03，允许 O(N^2).可能出现的最坏情况只要求平均复杂度为 0(对数 N)。

**3。运行时间:**
STL 的排序比 C 的 qsort 运行得更快，因为 C++ 的模板为特定的数据类型和特定的比较函数生成优化的代码。

STL 的排序比手工编码的快速排序快 20%到 50%，比 C qsort 库函数快 250%到 1000%。c 语言可能是最快的语言，但是 qsort 非常慢。

当我们试图在 C++ 14 上对一百万个整数进行排序时，C qsort()花费的时间是 0.247883 秒，C++ sort()花费的时间只有 0.086125 秒

```cpp
// C++ program to demonstrate performance of
// C qsort and C++ sort() algorithm
#include <bits/stdc++.h>
using namespace std;

// Number of elements to be sorted
#define N 1000000

// A comparator function used by qsort
int compare(const void * a, const void * b)
{
    return ( *(int*)a - *(int*)b );
}

// Driver program to test above functions
int main()
{
    int arr[N], dupArr[N];

    // seed for random input
    srand(time(NULL));

    // to measure time taken by qsort and sort
    clock_t begin, end;
    double time_spent;

    // generate random input
    for (int i = 0; i < N; i++)
        dupArr[i] = arr[i] = rand()%100000;

    begin = clock();
    qsort(arr, N, sizeof(int), compare);
    end = clock();

    // calculate time taken by C qsort function
    time_spent = (double)(end - begin) / CLOCKS_PER_SEC;

    cout << "Time taken by C qsort() - "
         << time_spent << endl;

    time_spent = 0.0;

    begin = clock();
    sort(dupArr, dupArr + N);
    end = clock();

    // calculate time taken by C++ sort
    time_spent = (double)(end - begin) / CLOCKS_PER_SEC;

    cout << "Time taken by C++ sort() - "
         << time_spent << endl;

    return 0;
}
```

输出:

```cpp
Time taken by C qsort() - 0.247883
Time taken by C++ sort() - 0.086125 
```

由于内联，C++ sort()在等效数据上比 qsort()快得多。默认情况下，整数容器上的 sort()将被编译为使用 std::less <int>:运算符()，该运算符将被内联，sort()将直接比较整数。另一方面，对于编译器未能优化的每次比较，qsort()将通过函数指针进行间接调用。</int>

**4。灵活性:**
STL 的排序适用于所有数据类型和不同的数据容器，如 C 数组、C++ 向量、C++ deques 等以及用户可以编写的其他容器。这种灵活性在 C.

**5 中是相当难达到的。安全性:**
与 qsort 相比，模板化排序更具类型安全性，因为它不像 qsort 那样需要通过不安全的 void 指针访问数据项。

**参考文献:**
[http://theory.stanford.edu/~amitp/rants/c++-vs-c](http://theory.stanford.edu/~amitp/rants/c++-vs-c)
[https://en . Wikipedia . org/wiki/Sort _(C % 2B % 2B)](https://en.wikipedia.org/wiki/Sort_(C%2B%2B))

本文由 **Aditya Goel** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息