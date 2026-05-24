# std::partial_sort_copy 在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdpartial_sort_copy-in-cpp/](https://www.geeksforgeeks.org/stdpartial_sort_copy-in-cpp/)

**[STD::partial _ sort](https://www.geeksforgeeks.org/stdpartial_sort-in-cpp/)**用于对整个集装箱内的范围进行排序。因此，如果我们想保持原始容器的完整，而只是将容器的排序子部分复制到另一个容器中，那么为此，我们可以使用 **std::partial_sort_copy** 。

就像 std::partial_sort 一样，partial_sort_copy()可以通过两种方式使用，如下所示:

1.  **Comparing elements using <:**

    语法:

    ```cpp
    Template 
    RandomAccessIterator partial_sort_copy (InputIterator first, InputIterator last,
                                            RandomAccessIterator result_first,
                                            RandomAccessIterator result_last);

    first: Input iterator to the first element in the container.
    last: Input iterator to the last element in the container.
    result_first: Random-Access iterator pointing to the initial
    position in the destination container.
    result_last: Random-Access iterator pointing to the final
    position in the destination container.

    Return Value: It returns an iterator pointing to the element that 
    follows the last element written in the result sequence.

    ```

    ```cpp
    // C++ program to demonstrate the use of
    // std::partial_sort_copy
    #include <iostream>
    #include <vector>
    #include <algorithm>
    using namespace std;
    int main()
    {
        vector<int> v = { 1, 1, 3, 10, 3, 3, 7, 7, 8 }, v1(3);

        vector<int>::iterator ip;

        // Using std::partial_sort_copy
        std::partial_sort_copy(v.begin(), v.end(), v1.begin(), v1.end());

        // Displaying the vector after applying
        // std::partial_sort_copy
        for (ip = v1.begin(); ip != v1.end(); ++ ip) {
            cout << *ip << " ";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    1 1 3

    ```

    在这里，因为我们声明 v1 的大小为 3，所以其中只存储了三个元素。

2.  **By comparing using a pre-defined function:**

    语法:

    ```cpp
    Template
     RandomAccessIterator partial_sort_copy (InputIterator first, InputIterator last,
                                             RandomAccessIterator result_first,
                                             RandomAccessIterator result_last,
                                             Compare comp); 
    Here, first, last, result_first and result_last are 
    the same as previous case.

    comp: Binary function that accepts two elements in the range 
    as arguments, and returns a value convertible to bool. The value 
    returned indicates whether the element passed as first 
    argument is considered to go before the second in the specific
    strict weak ordering it defines.
    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Return Value: It returns an iterator pointing to the element that 
    follows the last element written in the result sequence.

    ```

    ```cpp
    // C++ program to demonstrate the use of
    // std::partial_sort_copy
    #include <iostream>
    #include <algorithm>
    #include <vector>
    using namespace std;

    // Defining the BinaryFunction
    bool comp(int a, int b)
    {
        return (a < b);
    }

    int main()
    {
        vector<int> v = { 1, 1, 3, 10, 3, 3, 7, 7, 8 }, v1(7);

        vector<int>::iterator ip;

        // Using std::partial_sort_copy
        std::partial_sort_copy(v.begin(), v.end(), v1.begin(),
                               v1.end(), comp);

        // Displaying the vector after applying
        // std::partial_sort_copy
        for (ip = v1.begin(); ip != v1.end(); ++ ip) {
            cout << *ip << " ";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    1 1 3 3 3 7 7

    ```

**用在哪里？**

*   **For copying the sorted range:** So, whenever we want the original container to remain unchanged after sorting and the resultant of partial_sort to be stored inside another container, then we can use this.

    ```cpp
    // C++ program to demonstrate the use of
    // std::partial_sort_copy
    #include <iostream>
    #include <vector>
    #include <algorithm>
    using namespace std;
    int main()
    {
        vector<int> v = { 100, 45, 78, 23, 220 }, v1(5);

        vector<int>::iterator ip;

        // Using std::partial_sort_copy
        std::partial_sort_copy(v.begin(), v.end(), v1.begin(),
                               v1.end());

        // Displaying the vectors after applying
        // std::partial_sort_copy
        cout << "v = ";

        for (ip = v.begin(); ip != v.end(); ++ ip) {
            cout << *ip << " ";
        }

        cout << "\nv1 = ";
        for (ip = v1.begin(); ip != v1.end(); ++ ip) {
            cout << *ip << " ";
        }
        return 0;
    }
    ```

    输出:

    ```cpp
    v = 100 45 78 23 220
    v1 = 23 45 78 100 220

    ```

    所以，这里 v 保持不变，它的排序形式存储在 v1 中。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。