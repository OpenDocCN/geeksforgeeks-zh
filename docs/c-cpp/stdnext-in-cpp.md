# STD::c++ 中的 next

> 原文:[https://www.geeksforgeeks.org/stdnext-in-cpp/](https://www.geeksforgeeks.org/stdnext-in-cpp/)

**std::next** 返回一个迭代器，该迭代器在前进一定数量的位置后指向元素。它在头文件**中定义。**

**它**不修改它的参数**，并返回一个指定数量的参数的副本。如果它是一个[随机访问迭代器](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)，函数只使用一次运算符+或运算符–来前进。否则，该函数在复制的迭代器上重复使用递增或递减运算符(运算符++ 或运算符–),直到 n 个元素被推进。**

****语法:****

```cpp
**ForwardIterator next (ForwardIterator it,
       typename iterator_traits::difference_type n = 1);**
**it:** Iterator to the base position.
**difference_type:** It is the numerical type that represents 
distances between iterators of the ForwardIterator type.
**n:** Total no. of positions by which the
iterator has to be advanced. In the syntax, n is assigned
a default value 1 so it will atleast advance by 1 position.

**Returns:** It returns an iterator to the element 
n positions away from it. 
```

 ```cpp
// C++ program to demonstrate std::next
#include <iostream>
#include <iterator>
#include <deque>
#include <algorithm>
using namespace std;
int main()
{
    // Declaring first container
    deque<int> v1 = { 1, 2, 3, 4, 5, 6, 7 };

    // Declaring another container
    deque<int> v2 = { 8, 9, 10 };

    // Declaring an iterator
    deque<int>::iterator i1;

    // i1 points to 1
    i1 = v1.begin();

    // Declaring another iterator to store return
    // value and using std::next
    deque<int>::iterator i2;
    i2 = std::next(i1, 4);

    // Using std::copy
    std::copy(i1, i2, std::back_inserter(v2));
    // Remember, i1 stills points to 1
    // and i2 points to 5
    // v2 now contains 8 9 10 1 2 3 4

    // Displaying v1 and v2
    cout << "v1 = ";

    int i;
    for (i = 0; i < 7; ++ i) {
        cout << v1[i] << " ";
    }

    cout << "\nv2 = ";
    for (i = 0; i < 7; ++ i) {
        cout << v2[i] << " ";
    }

    return 0;
}
```

输出:

```cpp
v1 = 1 2 3 4 5 6 7
v2 = 8 9 10 1 2 3 4

```

**怎么会有帮助？**

*   **在列表中推进迭代器:**因为，列表支持[双向迭代器](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)，只能使用++ 和––运算符进行递增。所以，如果我们想让迭代器前进不止一个位置，那么使用 std::next 会非常有用。

    ```cpp
    // C++ program to demonstrate std::next
    #include <iostream>
    #include <iterator>
    #include <list>
    #include <algorithm>
    using namespace std;
    int main()
    {
        // Declaring first container
        list<int> v1 = { 1, 2, 3, 7, 8, 9 };

        // Declaring second container
        list<int> v2 = { 4, 5, 6 };

        list<int>::iterator i1;
        i1 = v1.begin();
        // i1 points to 1 in v1

        list<int>::iterator i2;
        // i2 = v1.begin() + 3;
        // This cannot be used with lists
        // so use std::next for this

        i2 = std::next(i1, 3);

        // Using std::copy
        std::copy(i1, i2, std::back_inserter(v2));
        // v2 now contains 4 5 6 1 2 3

        // Displaying v1 and v2
        cout << "v1 = ";

        int i;
        for (i1 = v1.begin(); i1 != v1.end(); ++ i1) {
            cout << *i1 << " ";
        }

        cout << "\nv2 = ";
        for (i1 = v2.begin(); i1 != v2.end(); ++ i1) {
            cout << *i1 << " ";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    v1 = 1 2 3 7 8 9
    v2 = 4 5 6 1 2 3  

    ```

    **解释:**在这里，只要看看如果我们想要只复制列表的一个选定部分，那么我们可以使用 std::next，因为否则我们不能使用任何具有列表支持的双向迭代器的+=、-=运算符。因此，我们使用了 std::next，并将迭代器直接提升了三个位置。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**