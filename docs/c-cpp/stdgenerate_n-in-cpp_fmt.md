# std::generate_n in C++

> 原文: [https://www.geeksforgeeks.org/stdgenerate_n-in-cpp/](https://www.geeksforgeeks.org/stdgenerate_n-in-cpp/)

`std::generate` 是一种 STL 算法，用于根据生成器函数生成数字，然后将这些值分配给容器中范围 `[first, last]` 内的元素。

生成器函数必须由用户定义，并被连续调用以分配数字。
现在，可以有一个场景，我们希望只给前 `n` 个元素赋值，为此我们有另一个 STL 算法 `std::generate_n`，其语法如下：

**模板函数:**

```cpp
OutputIterator generate_n (OutputIterator first, Size n, Generator gen);
```

- `first`: 指向容器起始位置的输出迭代器。
- `n`: 需要使用生成器函数赋值的元素数量。
- `gen`: 用于生成值的生成器函数。

**返回值:**
它不像 `std::generate` 那样返回 `void`，而是返回一个迭代器，指向最后一个被赋值元素之后的元素。

```cpp
// C++ program to demonstrate the use of std::generate_n
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

    // using std::generate_n
    std::generate_n(v1.begin(), 10, gen);

    vector<int>::iterator i1;
    for (i1 = v1.begin(); i1 != v1.end(); ++ i1) {
        cout << *i1 << " ";
    }
    return 0;
}
```

**输出:**

```
1 2 3 4 5 6 7 8 9 10
```

本文由 **姆里根德拉·辛格** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。