# STD::c++ 中的 stable _ partition

> 原文:[https://www.geeksforgeeks.org/stdstable_partition-in-c/](https://www.geeksforgeeks.org/stdstable_partition-in-c/)

**stable_partition( )** 算法排列由 start 和 end 定义的序列，使得 pfn 指定的谓词返回 true 的所有元素都出现在谓词返回 false 的元素之前。分区是稳定的。这意味着序列的相对顺序被保留。
**语法:**

```cpp
template 
BiIter stable_partition(BiIter start, BiIter end, UnPred pfn);

```

**参数:**

```cpp
start: the range of elements to reorder
end: the range of elements to reorder
pfn: User-defined predicate function object that 
defines the condition to be satisfied if an element is to be classified.
A predicate takes single argument and returns true or false.
Return Value: 
Returns an iterator to the beginning of the elements 
for which the predicate is false.

```

**该函数试图分配一个临时缓冲区。如果分配失败，则选择效率较低的算法。**
**例 1:**

```cpp
// CPP program to illustrate stable_partition
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main()
{
    vector<int> v{ 6, 9, 0, 1, 2, 7, 5, 8, 0 };
    stable_partition(v.begin(), v.end(), [](int n) {return n>0; });
    for (int n : v) {
        cout << n << ' ';
    }
    cout << '\n';
}
```

输出:

```cpp
6 9 1 2 7 5 8 0 0 

```

**例 2:**

```cpp
// CPP program to illustrate stable_partition
#include <iostream>
#include <algorithm> // std::stable_partition
#include <vector>

bool odd(int i) { return (i % 2) == 1; }

int main()
{
    std::vector<int> vct;

    for (int i = 1; i < 10; ++ i)
        vct.push_back(i); // 1 2 3 4 5 6 7 8 9

    std::vector<int>::iterator bound;
    bound = std::stable_partition(vct.begin(), vct.end(), odd);

    std::cout << "odd numbers:";
    for (std::vector<int>::iterator it = vct.begin(); it != bound; ++ it)
        std::cout << ' ' << *it;
    std::cout << '\n';

    std::cout << "evennumbers:";
    for (std::vector<int>::iterator it = bound; it != vct.end(); ++ it)
        std::cout << ' ' << *it;
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
odd numbers: 1 3 5 7 9
even numbers: 2 4 6 8

```

**例 3:**

```cpp
// CPP program to illustrate stable_partition
#include <algorithm>
#include <deque>
#include <functional>
#include <iostream>
#include <iterator>

template <class Arg>
struct is_even : public std::unary_function<Arg, bool> {
    bool operator()(const Arg& arg1) const
    {
        return (arg1 % 2) == 0;
    }
};

int main()
{
    typedef std::deque<int, std::allocator<int> > Deque;
    typedef std::ostream_iterator<int, char,
                                  std::char_traits<char> >
        Iter;

    const Deque::value_type a[] = { 1, 2, 3, 4, 5,
                                    6, 7, 8, 9, 10 };

    Deque d1(a + 0, a + sizeof a / sizeof *a);
    Deque d2(d1);

    std::cout << "Unpartitioned values: \t\t";
    std::copy(d1.begin(), d1.end(), Iter(std::cout, " "));

    std::partition(d2.begin(), d2.end(), is_even<int>());
    std::cout << "\nPartitioned values: \t\t";
    std::copy(d2.begin(), d2.end(), Iter(std::cout, " "));

    std::stable_partition(d1.begin(), d1.end(),
                          is_even<int>());
    std::cout << "\nStable partitioned values: \t";
    std::copy(d1.begin(), d1.end(), Iter(std::cout, " "));
    std::cout << std::endl;

    return 0;
}
```

**输出:**

```cpp
Unpartitioned values:         1 2 3 4 5 6 7 8 9 10 
Partitioned values:         10 2 8 4 6 5 7 3 9 1 
Stable partitioned values:     2 4 6 8 10 1 3 5 7 9 

```

**复杂性:**如果内存不足，则精确地结束-开始谓词的应用程序，如果内存充足，则最多(结束-开始)*日志(结束-开始)交换。

本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。