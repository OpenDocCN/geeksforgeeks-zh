# 标准::C++ 中的插入器

> 原文:[https://www.geeksforgeeks.org/stdinserter-in-cpp/](https://www.geeksforgeeks.org/stdinserter-in-cpp/)

**std::inserter** 构造一个插入迭代器，从 x 指向的位置开始，在 x 的连续位置插入新元素。它在头文件**中定义。**

**插入迭代器是一种特殊类型的**输出迭代器**，旨在允许通常覆盖元素(如复制)的算法在容器的特定位置自动插入新元素。
语法:**

```cpp
**std::inserter(Container& x, typename Container::iterator it);**
**x:** Container in which new elements will 
be inserted.
**it:** Iterator pointing to the insertion point.

**Returns:** An insert_iterator that inserts elements into 
x at the position indicated by it. 
```

```cpp
// C++ program to demonstrate std::inserter
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

    deque<int>::iterator i1;
    i1 = v2.begin() + 1;
    // i1 points to next element of 4 in v2

    // Using std::inserter inside std::copy
    std::copy(v1.begin(), v1.end(), std::inserter(v2, i1));
    // v2 now contains 4 1 2 3 5 6

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

**输出:**

```cpp
v1 = 1 2 3
v2 = 4 1 2 3 5 6 
```

****有什么帮助？****

*   ****Inserting values anywhere :** Now, just imagine, if we had to copy value into a container such as a vector, firstly, we had to move elements and then copy, but with the help of std::insert() we can insert at any position with ease.

    ```cpp
    // C++ program to demonstrate std::inserter
    #include <iostream>
    #include <iterator>
    #include <vector>
    #include <algorithm>
    using namespace std;
    int main()
    {
        // Declaring first container
        vector<int> v1 = { 1, 2, 3, 7, 8, 9 };

        // Declaring second container
        vector<int> v2 = { 4, 5, 6 };

        vector<int>::iterator i1;
        i1 = v2.begin() + 2;
        // i1 points to next element of 5 in v2

        // Using std::inserter inside std::copy
        std::copy(v1.begin(), v1.end(), std::inserter(v2, i1));
        // v2 now contains 4 5 1 2 3 7 8 9 6

        // Displaying v1 and v2
        cout << "v1 = ";

        int i;
        for (i = 0; i < 6; ++ i) {
            cout << v1[i] << " ";
        }

        cout << "\nv2 = ";
        for (i = 0; i < 9; ++ i) {
            cout << v2[i] << " ";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    v1 = 1 2 3 7 8 9
    v2 = 4 5 1 2 3 7 8 9 6

    ```

    **说明:**这里我们开始把 v1 复制成 v2，但不是从开始，而是在 v2 的第二个位置之后，也就是 5 之后，所以 v1 的所有元素都是在 5 之后，6 之前插入的。通过这种方式，我们可以很容易地在我们想要的地方插入价值。** 

****需要记住的要点:****

1.  **std::inserter 的缺陷之一是它只能与那些将 insert 作为其方法之一的容器一起使用**，如在 vector、list 和 deque 等情况下。****
2.  ****insert()vs std::inserter():**现在，您可能会认为 insert()和 STD::inserter()相似，但实际上并不相似。当你必须在算法中传递一个迭代器时，你应该像上面的例子一样使用 insert()方法，而对于在容器中正常插入值，可以使用 insert()方法。**
3.  **In place of using std::inserter, we can **create a insert_iterator** and then use it, as eventually, std::inserter returns a insert_iterator only.

    ```cpp
    // C++ program to demonstrate insert_iterator
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
        ii = v2.begin() + 1;
        // ii points after 4 in v2

        // Declaring a insert_iterator
        std::insert_iterator<std::deque<int> > i1(v2, ii);

        // Using the iterator in the copy()
        std::copy(v1.begin(), v1.end(), i1);
        // v2 now contains 4 1 2 3 5 6

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
    v2 = 4 1 2 3 5 6

    ```** 

**本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**