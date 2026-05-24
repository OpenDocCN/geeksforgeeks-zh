# 在 C++ 中使用 STL 对数组进行洗牌

> 原文:[https://www . geesforgeks . org/shuffle-a-array-use-STL-in-c/](https://www.geeksforgeeks.org/shuffle-an-array-using-stl-in-c/)

给定一个数组，任务是洗牌并打印整个数组。
**例**

```cpp
Input  (1, 2, 3, 4, 5, 6, 7}
Output  {3, 1, 6, 7, 2, 4, 5}

Input  (1, 2, 3}
Output  {3, 1, 2}
```

STL 包含两种方法，可以用来得到一个混洗的数组。这就是 [**shuffle()** 和**random _ shuffle()**T5。](https://www.geeksforgeeks.org/shuffle-vs-random_shuffle-c/) 

**洗牌**

该方法使用 *g* 作为统一随机数发生器，随机重新排列范围【第一个，最后一个】内的元素。它将每个元素的值与其他随机选取的元素的值进行交换。它确定通过调用 g()拾取的元素。
T3】模板 T5】

```cpp
template 
  void shuffle (RandomAccessIterator first, 
                RandomAccessIterator last, 
                URNG&& g)
{
  for (auto i=(last-first)-1; i>0; --i) {
    std::uniform_int_distribution d(0, i);
    swap (first[i], first[d(g)]);
  }
}
```

**实施**T2】

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to shuffle
// the given array
// using shuffle() method

#include <bits/stdc++.h>
using namespace std;

// Shuffle array
void shuffle_array(int arr[], int n)
{

    // To obtain a time-based seed
    unsigned seed = 0;

    // Shuffling our array
    shuffle(arr, arr + n,
            default_random_engine(seed));

    // Printing our array
    for (int i = 0; i < n; ++ i)
        cout << arr[i] << " ";
    cout << endl;
}

// Driver code
int main()
{

    int a[] = { 10, 20, 30, 40 };

    int n = sizeof(a) / sizeof(a[0]);

    shuffle_array(a, n);

    return 0;
}
```

**Output:** 

```cpp
30 10 20 40
```

**注意:**由于程序中使用的随机函数，每次输出可能会有所不同。

**随机 _ 洗牌**

该函数随机重新排列范围[第一个，最后一个]中的元素。它将每个元素的值与其他随机选取的元素交换。当提供时，函数 *gen* 确定在每种情况下选择哪个元素。否则，该函数会使用一些未指定的随机性来源。
T3】模板 T5】

```cpp
template 
  void random_shuffle (RandomAccessIterator first, 
                       RandomAccessIterator last,
                       RandomNumberGenerator& gen)
{
  iterator_traits::difference_type i, n;
  n = (last-first);
  for (i=n-1; i>0; --i) {
    swap (first[i], first[gen(i+1)]);
  }
}
```

**实施**T2】

## CPP14

```cpp
// C++ program to shuffle
// the given array
// using random_shuffle() method

#include <bits/stdc++.h>
using namespace std;

// Shuffle array
void shuffle_array(int arr[], int n)
{

    // To obtain a time-based seed
    unsigned seed = 0;

    // Shuffling our array using random_shuffle
    random_shuffle(arr, arr + n);

    // Printing our array
    for (int i = 0; i < n; ++ i)
        cout << arr[i] << " ";
    cout << endl;
}

// Driver code
int main()
{

    int a[] = { 10, 20, 30, 40 };

    int n = sizeof(a) / sizeof(a[0]);

    shuffle_array(a, n);

    return 0;
}
```

**Output:** 

```cpp
10 40 20 30
```

**注意:**由于程序中使用的随机函数，每次输出可能会有所不同。

**哪个更好？**

*   **shuffle** 在 C11++ 之后推出，使用的函数比 random _ shuffle 使用的 rand()要好。
*   shuffle 是对 random_shuffle 的改进，我们应该更喜欢使用前者以获得更好的结果。
*   如果我们不在 random_shuffle 中传递我们的随机生成函数，那么它将使用其未指定的随机值，由于这些值，所有连续的值都是相关的。