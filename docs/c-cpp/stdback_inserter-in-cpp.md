# STD::back _ insert in c++

> 原文:[https://www.geeksforgeeks.org/stdback_inserter-in-cpp/](https://www.geeksforgeeks.org/stdback_inserter-in-cpp/)

**std::back_inserter** 构造一个 back-insert 迭代器，在应用它的容器的末尾插入新元素。它在头文件**中定义。**

回插迭代器是一种特殊类型的**输出迭代器**，旨在允许通常覆盖元素(如复制)的算法在容器的末尾自动插入新元素。

**语法:**

```cpp
std::back_inserter (Container& x);

x: Container in which new elements will 
be inserted at the end.

Returns: A back_insert_iterator that inserts 
elements at the end of container x.

```

```cpp
// C++ program to demonstrate std::back_inserter
#include <iostream>
#include <iterator>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    // Declaring first container
    vector<int> v1 = { 1, 2, 3 };

    // Declaring second container for
    // copying values
    vector<int> v2 = { 4, 5, 6 };

    // Using std::back_inserter inside std::copy
    std::copy(v1.begin(), v1.end(), std::back_inserter(v2));
    // v2 now contains 4 5 6 1 2 3

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
v2 = 4 5 6 1 2 3

```

**有什么帮助？**

*   **不需要事先知道容器的大小:**这样的功能可以提供极大帮助的场景之一是，当我们不知道容器的大小，即有多少元素将被插入其中时，因此一种方法是使该容器具有极大的大小，但是**最有效的方法是在这种情况下使用 STD::back _ insider()**，而无需声明容器的大小。

    ```cpp
    // C++ program to demonstrate std::back_inserter
    #include <iostream>
    #include <iterator>
    #include <vector>
    #include <algorithm>
    using namespace std;
    int main()
    {
        // Declaring first container
        vector<int> v1 = { 1, 2, 3 };

        // Declaring second container without specifying
        // its size
        vector<int> v2;

        // Using std::back_inserter inside std::copy
        std::copy(v1.begin(), v1.end(), std::back_inserter(v2));
        // v2 now contains 1 2 3

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

    输出:

    ```cpp
    v1 = 1 2 3
    v2 = 1 2 3

    ```

    **解释:**在这里，我们必须将 v1 复制到 v2 中，但是假设我们处于不知道有多少元素将被复制到 v2 中的场景中，因此我们不会指定其大小，稍后将使用 std::back_inserter()复制到其中。

    **为什么不用 v2.begin()代替 back_inserter()？？**很多人会想，为什么我们没有用 v2.begin()来代替 std::back_inserter(v2)，那么你需要重新思考一下，既然我们没有声明 v2 的大小，那么里面就没有元素，所以就没有开头，所以，v2.begin()会在这里抛出一个错误。

**要记住的要点:**

1.  One of the pitfalls of STD::back _ inserter is that it can only be used with containers that use push_back as one of their methods, such as vector, list and deque.
2.  **push _ back () vs back _ inserter ():** Now, you may be thinking that push _ back () and back _ inserter are similar, but they are not. When you have to pass an iterator in the algorithm, you should use back_inserter as in the above example, and push_back () can be used for the values usually inserted at the end of the container.
3.  代替使用 std::back_inserter，我们可以**创建 back_insert_iterator** 然后作为最终使用，std::back_inserter 只返回 back_insert_iterator。

    ```cpp
    // C++ program to demonstrate back_insert_iterator
    #include <iostream>
    #include <iterator>
    #include <vector>
    #include <algorithm>
    using namespace std;
    int main()
    {
        // Declaring first container
        vector<int> v1 = { 1, 2, 3 };

        // Declaring second container for
        // copying values
        vector<int> v2 = { 4, 5, 6 };

        // Declaring a back_insert_iterator
        std::back_insert_iterator<std::vector<int> > back_i1(v2);

        // Using the iterator in the copy()
        std::copy(v1.begin(), v1.end(), back_i1);
        // v2 now contains 4 5 6 1 2 3

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
    v2 = 4 5 6 1 2 3

    ```

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。