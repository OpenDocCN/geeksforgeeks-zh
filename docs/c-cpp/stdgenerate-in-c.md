# std::在 C++ 中生成

> 原文:[https://www.geeksforgeeks.org/stdgenerate-in-c/](https://www.geeksforgeeks.org/stdgenerate-in-c/)

**std::generate** 顾名思义是一个 STL 算法，用于根据生成器函数生成数字，然后将这些值分配给容器中范围[第一个，最后一个]内的元素。

生成器函数必须由用户定义，并被连续调用以分配数字。

**模板功能:**

```cpp
void generate (ForwardIterator first, ForwardIterator last, Generator gen);

first: Forward iterator pointing to the first element of the container.
last: Forward iterator pointing to the last element of the container.
gen: A generator function, based upon which values will be assigned.

Returns: none
Since, it has a void return type, so it does not return any value.

```

```cpp
// C++ program to demonstrate the use of std::generate
#include <iostream>
#include <vector>
#include <algorithm>

// Defining the generator function
int gen()
{
    static int i = 0;
    return ++ i;
}

using namespace std;
int main()
{
    int i;

    // Declaring a vector of size 10
    vector<int> v1(10);

    // using std::generate
    std::generate(v1.begin(), v1.end(), gen);

    vector<int>::iterator i1;
    for (i1 = v1.begin(); i1 != v1.end(); ++ i1) {
        cout << *i1 << " ";
    }
    return 0;
}
```

输出:

```cpp
1 2 3 4 5 6 7 8 9 10

```

**下一步:**[STD::c++ 中的 generate _ n](https://www.geeksforgeeks.org/stdgenerate_n-in-c/)

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。