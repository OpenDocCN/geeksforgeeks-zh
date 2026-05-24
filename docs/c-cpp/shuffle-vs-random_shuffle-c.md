# c++ 中 shuffle vs random _ shuffle

> 原文:[https://www.geeksforgeeks.org/shuffle-vs-random_shuffle-c/](https://www.geeksforgeeks.org/shuffle-vs-random_shuffle-c/)

**[随机 _ 洗牌](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)**

它随机重新排列范围内的元素[第一个，最后一个]。
该函数将每个元素的值与其他随机选取的元素交换。如果提供了函数 gen，它将决定在每种情况下选择哪个元素。否则，该函数会使用一些未指定的随机性来源。

```cpp
// CPP program Illustrating the
// use of random_shuffle
#include <bits/stdc++.h>
using namespace std;

// random generator function
int randomfunc(int j)
{
    return rand() % j;
}

int main()
{
    srand(unsigned(time(0)));
    vector<int> arr;

    // set some values:
    for (int j = 1; j < 10; ++ j)

        // 1 2 3 4 5 6 7 8 9
        arr.push_back(j);

    // using built-in random generator
    random_shuffle(arr.begin(), arr.end());

    // using randomfunc
    random_shuffle(arr.begin(), arr.end(), randomfunc);

    // print out content:
    cout << "arr contains:";
    for (auto i = arr.begin(); i != arr.end(); ++ i)
        cout << ' ' << *i;

    cout << endl;

    return 0;
}
```

输出:

```cpp
arr contains: 5 8 1 7 9 6 4 3 2

```

**洗牌**

使用 g 作为统一随机数生成器，随机重新排列范围[第一个，最后一个]中的元素。
该函数将每个元素的值与其他随机选取的元素的值进行交换。该函数确定通过调用 g()选择的元素。

```cpp
// CPP program Illustrating
// the use of shuffle
#include <bits/stdc++.h>
using namespace std;

// Driver Program
int main()
{
    array<int, 5> s{ 1, 2, 3, 4, 5 };

    // To obtain a time-based seed
    unsigned seed = 0;

    // Use of shuffle
    shuffle(s.begin(), s.end(), default_random_engine(seed));

    cout << "shuffled elements are:";
    for (int& i : s)
        cout << ' ' << i;
    cout << endl;

    return 0;
}
```

输出:

```cpp

shuffled elements are: 3 1 5 4 2

```

**shuffle 和 random_shuffle c++ 有什么区别？**

1.  唯一不同的是 **random_shuffle** 使用 **rand()** 函数对物品进行随机化，而 **shuffle** 使用 **urng** 这是一个更好的随机生成器，不过在 random_shuffle 的特定重载下，我们可以得到相同的行为(与 shuffle 一样)。
2.  shuffle 是对 random_shuffle 的改进，我们应该更喜欢使用前者以获得更好的结果。
3.  **Example of Swapping Variables using both**
    **random shuffle:**

    ```cpp
    template (class RandomIt, class RandomFunc)
    void random_shuffle(RandomIt first, RandomIt last, RandomFunc&& r)
    {
        typename iterator_traits::difference_type i, n;
        n = last - first;
        for (i = n-1; i > 0; --i) {
            using std::swap;
            swap(first[i], first[r(i+1)]);
        }
    }

    ```

    **洗牌:**

    ```cpp
    template void shuffle(RandomIt first, RandomIt last, 
                 UniformRandomBitGenerator&& g)
    {
        typedef typename iterator_traits::difference_type diff_t;
        typedef uniform_int_distribution distr_t;
        typedef typename distr_t::param_type param_t;

        distr_t D;
        diff_t n = last - first;
        for (diff_t i = n-1; i > 0; --i) {
            using swap;
            swap(first[i], first[D(g, param_t(0, i))]);
        }
    }
    ```

本文由 **[香巴拉维·辛格](https://www.facebook.com/shambhavi.singh.1217)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。