# 标准::C++ 中的 min _ element

> 原文:[https://www.geeksforgeeks.org/stdmin_element-in-cpp/](https://www.geeksforgeeks.org/stdmin_element-in-cpp/)

为了计算给定列表中所有元素中的最小元素，我们有 [std::min](https://www.geeksforgeeks.org/stdmin-in-cpp/) ，但是如果我们想要找到的不是整个列表中的最小元素，而是列表的**子部分**中的最小元素，该怎么办。为了达到这个目的，我们在 C++ 中有 std::min_element。

std::min_element 在头文件<algorithm>中定义，它返回一个迭代器，指向范围[第一个，最后一个]中值最小的元素。</algorithm>

不同于可以三种方式使用的 std::min，std::min_element 可以两种方式**使用。可以使用运算符<(第一个版本)或预定义函数(第二个版本)进行比较。如果一个以上的元素满足最小的条件，迭代器返回指向第一个这样的元素。
两个版本定义如下:**

1.  ****使用“<”比较元素:**
    语法:**

```cpp
**template 
ForwardIterator min_element (ForwardIterator first, ForwardIterator last);**

**first:** Forward iterator pointing to the beginning of the range.
**last:** Forward iterator pointing to the end of the range.

**Return Value:** It return a pointer to the smallest 
element in the range, and in case if there are more than one such element,
then it points to the first one.
It points to the last in case the range is empty. 
```

```cpp
// C++ program to demonstrate the use of std::min_element
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int v[] = { 9, 4, 7, 2, 5, 10, 11, 12, 1, 3, 6 };

    // Finding the minimum value between the third and the
    // fifth element

    int* i1;
    i1 = std::min_element(v + 2, v + 5);

    cout << *i1 << "\n";
    return 0;
}
```

**输出:**

```cpp
2 
```

*   ****For comparison based on a pre-defined function:**

    语法:

    ```cpp
    template 
    ForwardIterator min_element (ForwardIterator first, ForwardIterator last,
                                 Compare comp);
    Here, first and last are the same as previous case.
    comp: Binary function that accepts two elements 
    in the range as arguments, and returns a value convertible to bool.
    The value returned indicates whether the element passed as first 
    argument is considered less than the second.
    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Return Value: It return a pointer to the smallest element 
    in the range, and in case if there are more than one such element,
    then it points to the first one.
    It points to the last in case the range is empty.

    ```

    ```cpp
    // C++ program to demonstrate the use of std::min_element
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

        // Finding the minimum value between the third and the
        // ninth element

        int* i1;
        i1 = std::min_element(v + 2, v + 9, comp);

        cout << *i1 << "\n";
        return 0;
    }
    ```

    输出:

    ```cpp
    1

    ```

    **相关文章:**

    *   [标准::max_element](https://www.geeksforgeeks.org/stdmax_element-in-cpp/)
    *   [标准::最大值](https://www.geeksforgeeks.org/stdmax-in-cpp/)
    *   [标准::分钟](https://www.geeksforgeeks.org/stdmin-in-cpp/)
    *   [标准::相等](https://www.geeksforgeeks.org/stdequal-in-cpp/)

    本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**