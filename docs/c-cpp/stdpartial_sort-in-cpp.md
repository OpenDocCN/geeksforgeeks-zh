# std::partial_sort in C++

> 原文:[https://www.geeksforgeeks.org/stdpartial_sort-in-cpp/](https://www.geeksforgeeks.org/stdpartial_sort-in-cpp/)

**[【STD::sort】](https://www.geeksforgeeks.org/sort-c-stl/)**用于对容器内存在的元素进行排序。其中的一个变体是 **std::partial_sort** ，它不是用于对整个范围进行排序，而是仅用于对其中的一个子部分进行排序。

它重新排列范围[第一个，最后一个]中的元素，中间之前的元素按升序排序，而中间之后的元素没有任何特定的顺序。

它有两种使用方式，如下所示:

1.  **使用<比较元素:**

语法:

```cpp
Template 
void partial_sort (RandomAccessIterator first, RandomAccessIterator middle,
                   RandomAccessIterator last); 
first: Random-Access iterator to the first element in the container.
last: Random-Access iterator to the last element in the container.
middle: Random-Access iterator pointing to the element in the 
range [first, last), that is used as the upper boundary for the elements 
to be sorted.

Return Value: It has a void return type, so it does not return any value.

```

```cpp
// C++ program to demonstrate the use of
// std::partial_sort
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 1, 3, 1, 10, 3, 3, 7, 7, 8 }, i;

    vector<int>::iterator ip;

    // Using std::partial_sort
    std::partial_sort(v.begin(), v.begin() + 3, v.end());

    // Displaying the vector after applying
    // std::partial_sort
    for (ip = v.begin(); ip != v.end(); ++ ip) {
        cout << *ip << " ";
    }

    return 0;
}
```

输出:

```cpp
1 1 3 10 3 3 7 7 8 

```

这里只有前三个元素从第一个到中间排序，这里第一个是 v.begin()，中间是 v.begin() + 3，其余都没有任何顺序。

*   **By comparing using a pre-defined function:**

    语法:

    ```cpp
    Template
     void partial_sort (RandomAccessIterator first, RandomAccessIterator middle,
                        RandomAccessIterator last, Compare comp); 
    Here, first, middle and last are the same as previous case.

    comp: Binary function that accepts two elements in the range 
    as arguments, and returns a value convertible to bool. The value 
    returned indicates whether the element passed as first 
    argument is considered to go before the second in the specific
    strict weak ordering it defines.
    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Return Value: It has a void return type, so it does not return any value.

    ```

    ```cpp
    // C++ program to demonstrate the use of
    // std::partial_sort
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
        vector<int> v = { 1, 3, 1, 10, 3, 3, 7, 7, 8 }, i;

        vector<int>::iterator ip;

        // Using std::partial_sort
        std::partial_sort(v.begin(), v.begin() + 3, v.end(), comp);

        // Displaying the vector after applying
        // std::partial_sort
        for (ip = v.begin(); ip != v.end(); ++ ip) {
            cout << *ip << " ";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    1 1 3 10 3 3 7 7 8 

    ```

    **哪里可以用？**

    1.  **Finding the largest element:** Since, with std::partial_sort, we can partially sort the container till whichever position we would like to. So, if we just **sort the first position and use a function object** , we can find the largest element, without having to sort the entire container.

        ```cpp
        // C++ program to demonstrate the use of
        // std::partial_sort
        #include <iostream>
        #include <algorithm>
        #include <vector>
        using namespace std;
        int main()
        {
            vector<int> v = { 10, 45, 60, 78, 23, 21, 30 };

            vector<int>::iterator ip;

            // Using std::partial_sort
            std::partial_sort(v.begin(), v.begin() + 1, v.end(),
                              greater<int>());

            // Displaying the largest element after applying
            // std::partial_sort

            ip = v.begin();
            cout << "The largest element is = " << *ip;

            return 0;
        }
        ```

        输出:

        ```cpp
        The largest element is = 78

        ```

    2.  **Finding the smallest element:** Similar to finding the largest element, we can also find the smallest element in the container in the previous example.

        ```cpp
        // C++ program to demonstrate the use of
        // std::partial_sort
        #include <iostream>
        #include <algorithm>
        #include <vector>
        using namespace std;
        int main()
        {
            vector<int> v = { 10, 45, 60, 78, 23, 21, 3 };

            vector<int>::iterator ip;

            // Using std::partial_sort
            std::partial_sort(v.begin(), v.begin() + 1, v.end());

            // Displaying the smallest element after applying
            // std::partial_sort

            ip = v.begin();
            cout << "The smallest element is = " << *ip;

            return 0;
        }
        ```

        输出:

        ```cpp
        The smallest element is = 3

        ```

**点记:**

*   **std::sort() vs std::partial_sort():** Some of you might think that why are we using std::partial_sort, in place we can use std::sort() for the limited range, but remember, if we use std::sort with a partial range, then only elements within that range will be considered for sorting, while all other elements outside the range will not be considered for this purpose, whereas with std::partial_sort(), all the elements will be considered for sorting.

    ```cpp
    // C++ program to demonstrate the use of
    // std::partial_sort
    #include <iostream>
    #include <algorithm>
    #include <vector>
    using namespace std;
    int main()
    {
        vector<int> v = { 10, 45, 60, 78, 23, 21, 3 }, v1;

        int i;
        v1 = v;
        vector<int>::iterator ip;

        // Using std::partial_sort
        std::partial_sort(v.begin(), v.begin() + 2, v.end());

        // Using std::sort()
        std::sort(v1.begin(), v1.begin() + 2);

        cout << "v = ";
        for (i = 0; i < 2; ++ i) {
            cout << v[i] << " ";
        }

        cout << "\nv1 = ";
        for (i = 0; i < 2; ++ i) {
            cout << v1[i] << " ";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    v = 3 10
    v1 = 10 45

    ```

    **说明:**这里，我们对 v 应用了 std::partial_sort，对 v1 应用了 std::sort，一直到第二个位置。现在，您可以理解 std::sort 只对给定范围内的元素进行排序，而 partial_sort 考虑了整个容器，但只对前两个位置进行排序。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。