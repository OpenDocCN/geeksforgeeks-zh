# 标准::C++ 中的 prev

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdprev-in-CPP/

**std::prev** 返回一个迭代器，该迭代器在反向前进一定数量的位置后指向元素。它在头文件**中定义。**

**它**返回一个参数**的副本，该参数向后前进指定的量。如果是随机访问迭代器，函数只使用一次运算符+或运算符–来推进。否则，该函数在复制的迭代器上重复使用递增或递减运算符(运算符++ 或运算符–-)，直到 n 个元素被推进。**

**语法:**

```cpp
**BidirectionalIterator prev (BidirectionalIterator it,
       typename iterator_traits::difference_type n = 1);**
**it:** Iterator to the base position.
**difference_type:** It is the numerical type that represents 
distances between iterators of the BidirectionalIterator type.
**n:** Total no. of positions by which the
iterator has to be advanced. In the syntax, n is assigned
a default value 1 so it will atleast advance by 1 position.

**Returns:** It returns an iterator to the element 
n positions before it. 
```

 ```cpp
// C++ program to demonstrate std::prev
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
    // value and using std::prev
    deque<int>::iterator i2;
    i2 = std::prev(v1.end(), 3);

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

*   **在列表中移动迭代器:**因为，列表支持[双向迭代器](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)，只能通过使用++ 和––运算符来递增。所以，如果我们想让迭代器前进一个以上的位置，那么 **std::next** 如果我们想减少迭代器，那么 std::prev 会非常有用。

    ```cpp
    // C++ program to demonstrate std::prev
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
        // i2 = v1.end() - 3;
        // This cannot be used with lists
        // so use std::prev for this

        i2 = std::prev(v1.end(), 3);

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

    **解释:**在这里，只要看看如果我们想要只复制列表的一个选定部分，那么我们可以使用 std::prev，因为否则我们不能使用任何具有列表支持的双向迭代器的+=、-=运算符。因此，我们使用了 std::prev，并直接将迭代器从末尾向后移动了三个位置。

**我们能用 [std::next](https://www.geeksforgeeks.org/stdnext-in-cpp/) 代替 std::prev 吗？**

std::prev 可能会出现的一个常见查询是，可以将 std::next 与一个负参数一起使用，以向后移动迭代器。嗯，答案是**是的**。

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
    i2 = std::next(v1.end(), -3);

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

**解释:**所以，我们刚刚用 std::next 代替了 std::prev，并且在这里将第二个参数从 3 改为-3，它仍然服务于相同的目的。

我们也可以使用 std::next，但是有两件事需要记住:

*   Because std::next has a parameter as a forward iterator in their syntax, if we want to use negative numbers to advance that iterator, then it should be **or at least a bidirectional iterator** .
*   Although std::next can also be used, **STD:: prev () will be easier to read** when the intention is to move backward specifically.

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**