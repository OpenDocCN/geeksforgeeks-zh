# std::find_if，std::find_if_not in C++

> 原文:[https://www . geesforgeks . org/stdfind _ if-stdfind _ if _ not-in-c/](https://www.geeksforgeeks.org/stdfind_if-stdfind_if_not-in-c/)

**std :: find_if**

返回范围[第一个，最后一个]中第一个元素的迭代器，pred(一元函数)为该元素返回 **true** 。如果没有找到这样的元素，函数返回 last。
**功能模板:**

```cpp
InputIterator find_if (InputIterator first, InputIterator last, UnaryPredicate pred);

first, last :range which contains all the elements between first
and last, including the element pointed by first but
not the element pointed by last.

pred : Unary function that accepts an element in the range
as argument and returns a value in boolean.

Return value :
Returns an iterator to the first element in the range
[first, last] for which pred(function) returns true. If
no such element is found, the function returns last.

```

**标准::find_if_not**

将迭代器返回到 pred(一元函数)返回 **false** 的[第一个，最后一个]范围内的第一个元素。如果没有找到这样的元素，函数返回 last。
**功能模板:**

```cpp
InputIterator find_if_not (InputIterator first, InputIterator last, UnaryPredicate pred);

Return value :
Returns an iterator to the first element in the range
[first, last] for which pred(function) returns false.

```

```cpp
// CPP program to illustrate
// std::find_if and std::find_if_not
#include <bits/stdc++.h>

// Returns true if argument is odd
bool IsOdd(int i)
{
    return i % 2;
}

// Driver code
int main()
{
    std::vector<int> vec{ 10, 25, 40, 55 };

    // Iterator to store the position of element found
    std::vector<int>::iterator it;

    // std::find_if
    it = std::find_if(vec.begin(), vec.end(), IsOdd);
    std::cout << "The first odd value is " << *it << '\n';

        // Iterator to store the position of element found
        std::vector<int>::iterator ite;

    // std::find_if_not
    ite = std::find_if_not(vec.begin(), vec.end(), IsOdd);

    std::cout << "The first non-odd(or even) value is " << *ite << '\n';

        return 0;
}
```

输出:

```cpp
The first odd value is 25
The first non-odd(or even) value is 10

```

**相关文章:**

*   [标准::搜索](https://www.geeksforgeeks.org/stdsearch-in-c/)
*   [标准::查找](https://www.geeksforgeeks.org/stdfind-in-c/)
*   [标准::第 n _ 元素](https://www.geeksforgeeks.org/stdnth_element-in-cpp/)
*   [std::find_end](https://www.geeksforgeeks.org/stdfind_end-in-cpp/)

本文由 **[沙钦·毕斯特](https://www.linkedin.com/in/sachin-bisht-984b5013a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。