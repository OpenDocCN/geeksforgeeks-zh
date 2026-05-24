# STD::front _ insert in c++

> 原文:[https://www.geeksforgeeks.org/stdfront_inserter-in-cpp/](https://www.geeksforgeeks.org/stdfront_inserter-in-cpp/)

**std::front_inserter** 构造一个 front-insert 迭代器，在应用它的容器的前面插入新元素。它在头文件**中定义。**

前置插入迭代器是一种特殊类型的**输出迭代器**，旨在允许通常覆盖元素(如复制)的算法在容器的开头自动插入新元素。它与 **std::back_inserter 完全相反。**

**语法:**

```cpp
std::front_inserter (Container& x);

x: Container in which new elements will 
be inserted at the beginning.

Returns: A front_insert_iterator that inserts 
elements at the beginning of container x.

```

```cpp
// C++ program to demonstrate std::front_inserter
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

    // Using std::front_inserter inside std::copy
    std::copy(v1.begin(), v1.end(), std::front_inserter(v2));
    // v2 now contains 3 2 1 4 5 6

    // Displaying v1 and v2
    cout << "v1 = ";

    int i;
    for (i = 0; i < 3; ++ i) {
        cout << v1[i] << " ";
    }

    cout << "\nv2 = ";
    for (i = 0; i < 6; ++ i) {
        cout << v2[i] << " ";
    }

    return 0;
}
```

输出:

```cpp
v1 = 1 2 3
v2 = 3 2 1 4 5 6 

```

**有什么帮助？**

*   **Invert a container:** Now, because std::front_inserter inserts new elements at the beginning of the container, we can perform the **task of reverse_copy () with the help of copy (), so that we will create another container containing the inversion of the current container.

    ```cpp
    // C++ program to demonstrate std::front_inserter
    #include <iostream>
    #include <iterator>
    #include <deque>
    #include <algorithm>
    using namespace std;
    int main()
    {
        // Declaring first container
        deque<int> v1 = { 1, 2, 3 };

        // Declaring second container
        // for storing the reverse
        deque<int> v2;

        // Using std::front_inserter inside std::copy
        std::copy(v1.begin(), v1.end(), std::front_inserter(v2));
        // v2 now contains 3 2 1

        // Displaying v1 and v2
        cout << "v1 = ";

        int i;
        for (i = 0; i < 3; ++ i) {
            cout << v1[i] << " ";
        }

        cout << "\nv2 = ";
        for (i = 0; i < 3; ++ i) {
            cout << v2[i] << " ";
        }

        return 0;
    }
    ```

    Output:

    ```cpp
    v1 = 1 2 3
    v2 = 3 2 1

    ```

    **Explanation:** Here, we started to copy v1 to v2, but from the beginning, so every time a new element arrives, it is inserted at the beginning, so that the last element inserted becomes the first element in the new container, so that we can reverse the container's.** 

**要记住的要点:**

1.  One of the pitfalls of STD::front _ insert is that it can only be used with containers that use push_front as one of their methods, just like in the case of list and deque, it **cannot be used with vectors.**
2.  **push _ front () vs front _ insider ():** Now, you may be thinking that push _ front () and front _ insider are similar, but they are not. When you have to pass an iterator in the algorithm, you should use front_inserter as in the above example, and in order to insert the value at the beginning of the container normally, you can use push_front ().
3.  代替使用 STD::front _ insert，我们可以**创建一个 front_insert_iterator** 然后使用它，因为最终 STD::front _ insert 只返回一个 front_insert_iterator。

    ```cpp
    // C++ program to demonstrate front_insert_iterator
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

        // Declaring a front_insert_iterator
        std::front_insert_iterator<std::deque<int> > front_i1(v2);

        // Using the iterator in the copy()
        std::copy(v1.begin(), v1.end(), front_i1);
        // v2 now contains 3 2 1 4 5 6

        // Displaying v1 and v2
        cout << "v1 = ";

        int i;
        for (i = 0; i < 3; ++ i) {
            cout << v1[i] << " ";
        }

        cout << "\nv2 = ";
        for (i = 0; i < 6; ++ i) {
            cout << v2[i] << " ";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    v1 = 1 2 3
    v2 = 3 2 1 4 5 6

    ```

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。