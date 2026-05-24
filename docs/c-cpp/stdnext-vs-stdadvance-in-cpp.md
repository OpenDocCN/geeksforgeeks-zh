# STD::next vs STD::c++ 中的 advance

> 原文:[https://www.geeksforgeeks.org/stdnext-vs-stdadvance-in-cpp/](https://www.geeksforgeeks.org/stdnext-vs-stdadvance-in-cpp/)

[std::advance](https://www.geeksforgeeks.org/stdadvance-in-cpp/) 和 [std::next](https://www.geeksforgeeks.org/stdnext-in-cpp/) 用于将迭代器前进一定的位置，这样我们就可以让迭代器指向一个想要的位置。虽然两者有着相同的目的，但是它们的实现方式却各不相同。这使得我们理解两者之间的区别变得很重要。
在 C++ 11 中，默认情况下，std::next()将前进**一**，而 std::advance()需要**距离**。

1.  **句法差异:**STD::advance 和 std::next 的句法是:

    ```cpp
    // Definition of std::advance()
    template
    void advance( InputIt& it, Distance n );

    it: Iterator to be advanced
    n: Distance to be advanced

    ```

    ```cpp
    // Definition of std::next()
    ForwardIterator next (ForwardIterator it,
           typename iterator_traits::difference_type n = 1);

    it: Iterator pointing to base position
    n: Distance to be advanced from base position.

    ```

    *   **返回类型:** [std::advance](https://www.geeksforgeeks.org/stdadvance-in-cpp/) 不返回任何内容，而 [std::next](https://www.geeksforgeeks.org/stdnext-in-cpp/) 从给定的基本位置前进 n 个位置后返回一个迭代器。
    *   正如在 [std::next()](https://www.geeksforgeeks.org/stdnext-in-cpp/) 的语法中，它将**至少使迭代器前进一个位置**，即使我们没有指定它必须前进的位置，因为它有默认值 1，而如果我们使用 [std::advance](https://www.geeksforgeeks.org/stdadvance-in-cpp/) ，它没有这样的默认参数。
2.  **工作**
    *   **Argument Modification:** [std::advance](https://www.geeksforgeeks.org/stdadvance-in-cpp/) modifies it arguments such that it points to the desired position, whereas, [std::next](https://www.geeksforgeeks.org/stdnext-in-cpp/) does not modify its argument, infact it returns a new iterator pointing to the desired position.

        ```cpp
        // C++ program to demonstrate
        // std::advance vs std::next
        #include <iostream>
        #include <iterator>
        #include <deque>
        #include <algorithm>
        using namespace std;
        int main()
        {
            // Declaring first container
            deque<int> v1 = { 1, 2, 3 };

            // Declaring second container for
            // copying values
            deque<int> v2 = { 4, 5, 6 };

            deque<int>::iterator ii;
            ii = v1.begin();
            // ii points to 1 in v1

            deque<int>::iterator iii;
            iii = std::next(ii, 2);
            // ii not modified

            // For std::advance
            // std::advance(ii, 2)
            // ii modified and now points to 3

            // Using copy()
            std::copy(ii, iii, std::back_inserter(v2));
            // v2 now contains 4 5 6 1 2

            // Displaying v1 and v2
            cout << "v1 = ";

            int i;
            for (i = 0; i < 3; ++ i) {
                cout << v1[i] << " ";
            }

            cout << "\nv2 = ";
            for (i = 0; i < 5; ++ i) {
                cout << v2[i] << " ";
            }

            return 0;
        }
        ```

        输出:

        ```cpp
        v1 = 1 2 3
        v2 = 4 5 6 1 2 

        ```

        **解释:**可以看到，我们想让 ii 指向它所指向的位置前面的 2 个空格，所以如果我们使用 std::advance ii 将指向前面的两个空格，而如果我们使用 std::next，那么 ii 将不会前进，而是返回一个指向新位置的迭代器，并存储在 iii 中。

3.  **先决条件:** [std::next](https://www.geeksforgeeks.org/stdnext-in-cpp/) 要求作为参数传递的迭代器至少是[前向迭代器](https://www.geeksforgeeks.org/forward-iterators-in-cpp/)的类型，而 [std::advance](https://www.geeksforgeeks.org/stdadvance-in-cpp/) 没有这样的限制，因为它可以与任何迭代器一起工作，甚至与[输入迭代器](https://www.geeksforgeeks.org/input-iterators-in-cpp/)一起工作，或者比它更好。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。