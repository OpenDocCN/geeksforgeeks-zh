# c++ 中的 max _ element

> 原文:[https://www.geeksforgeeks.org/max_element-in-cpp/](https://www.geeksforgeeks.org/max_element-in-cpp/)

我们有 [std::max](https://www.geeksforgeeks.org/stdmax-in-cpp/) 来查找最多 2 个或更多的元素，但是如果我们想在数组、向量、列表或子节中查找最大的元素呢。为了达到这个目的，我们在 C++ 中有 std::max_element。
 **std::max_element** 在头文件<algorithm>中定义，它返回一个迭代器，指向范围【第一个，最后一个】中值最大的元素。</algorithm>

std::max_element 有两种使用方式。可以使用**运算符<** (第一版)或使用**预定义函数**(第二版)进行比较。如果一个以上的元素满足最大的条件，迭代器返回指向第一个这样的元素。

**这两个版本的定义如下:**

1.  **Use "
    " syntax to compare elements:: < >**

```cpp
template <class forwarditerator="">
ForwardIterator max_element (ForwardIterator first, ForwardIterator last);</class>

first: Forward iterator pointing to the beginning of the range.
last: Forward iterator pointing to the end of the range.

Return Value: It returns a pointer to the largest 
element in the range, and in case if there are more than 
one such element, then it points to the first one.

It points to the last in case the range is empty.

```

```cpp
// C++ program to demonstrate the use of std::max_element
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int v[] = { 'a', 'c', 'k', 'd', 'e', 'f', 'h' };

    // Finding the maximum value between the first and the
    // fourth element

    int* i1;
    i1 = std::max_element(v, v + 4);

    cout << char(*i1) << "\n";
    return 0;
}
```

输出:

```cpp
k

```

*   **For comparison based on a pre-defined function:**
    Syntax:

    ```cpp
    template <class forwarditerator="" class="" compare="">
    ForwardIterator max_element (ForwardIterator first, ForwardIterator last,
                                 Compare comp);</class>
    Here, first and last are the same as previous case.
    comp: Binary function that accepts two elements 
    in the range as arguments, and returns a value convertible to bool.

    The value returned indicates whether the element passed as first argument 
    is considered less than the second.
    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Return Value: It returns a pointer to the largest element 
    in the range, and in case if there are more than one such element,
    then it points to the first one.
    It points to the last in case the range is empty.

    ```

    ```cpp
    // C++ program to demonstrate the use of std::max_element
    #include <iostream>
    #include <algorithm>
    using namespace std;

    // Defining the BinaryFunction
    bool comp(int a, int b)
    {
        return (a < b);
    }

    int main()
    {
        int v[] = { 9, 4, 7, 2, 5, 10, 11, 12, 1, 3, 6 };

        // Finding the maximum value between the third and the
        // ninth element

        int* i1;
        i1 = std::max_element(v + 2, v + 9, comp);

        cout << *i1 << "\n";
        return 0;
    }
    ```

    输出:

    ```cpp
    12

    ```

    **相关文章:**

    *   [标准::最大值](https://www.geeksforgeeks.org/stdmax-in-cpp/)
    *   [标准::分钟](https://www.geeksforgeeks.org/stdmin-in-cpp/)
    *   [标准::相等](https://www.geeksforgeeks.org/stdequal-in-cpp/)
    *   [标准::C++ 中的 min _ element](https://www.geeksforgeeks.org/stdmin_element-in-cpp/)

    本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。