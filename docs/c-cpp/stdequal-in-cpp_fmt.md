# std::equal() 在 C++ 中

> 原文: [https://www.geeksforgeeks.org/stdequal-in-cpp/](https://www.geeksforgeeks.org/stdequal-in-cpp/)

`std::equal()` 有助于将 `[first_1, last_1]` 范围内的元素与从 `first_2` 开始的范围内的元素进行比较。

## 语法 1:

```cpp
template<class InputIterator1, class InputIterator2>
  bool equal (InputIterator1 first1, InputIterator1 last1,
              InputIterator2 first2)
```

`first_1`, `last_1`：第一个序列的初始和最终位置。所有元素都存在于范围 `[first_1, last_1)` 内。
`first2`：第二个序列的初始位置。

返回值：
如果两个范围内的所有元素都匹配，则返回 `true`；否则返回 `false`。

```cpp
// C++ program illustrating
// use of bool equal (InputIterator1 first1, InputIterator1 last1,
// InputIterator2 first2)

#include <bits/stdc++.h>

int main()
{
    int v1[] = { 10, 20, 30, 40, 50 };
    std::vector<int> vector_1 (v1, v1 + sizeof(v1) / sizeof(int) );

    // Printing vector1
    std::cout << "Vector contains : ";
    for (unsigned int i = 0; i < vector_1.size(); i++)
        std::cout << " " << vector_1[i];
    std::cout << "\n";

    // using std::equal()
    // Comparison within default constructor
    if ( std::equal (vector_1.begin(), vector_1.end(), v1) )
        std::cout << "The contents of both sequences are equal.\n";
    else
        printf("The contents of both sequences differ.");

}
```

**输出:**

```cpp
Vector contains :  10, 20, 30, 40, 50
The contents of both sequences are equal.
```

## 语法 2:

```cpp
template<class InputIterator1, class InputIterator2, class BinaryPredicate>
  bool equal (InputIterator1 first1, InputIterator1 last1,
              InputIterator2 first2, BinaryPredicate pred);
```

`first_1`, `last_1`：第一个序列的初始和最终位置。所有元素都存在于范围 `[first_1, last_1)` 内。
`first2`：第二个序列的初始位置。
`pred`：接受两个元素作为参数并返回可转换为布尔值的值的二元函数。

返回值：
如果两个范围内的所有元素都匹配，则返回 `true`；否则返回 `false`。

```cpp
// C++ program illustrating
// use of bool equal (InputIterator1 first1, InputIterator1 last1,
// InputIterator2 first2, BinaryPredicate pred);

#include <bits/stdc++.h>

bool pred(int i, int j)
{
    return (i != j);
}

int main()
{
    int v1[] = { 10, 20, 30, 40, 50 };
    std::vector<int> vector_1 (v1, v1 + sizeof(v1) / sizeof(int) );

    // Printing vector1
    std::cout << "Vector contains : ";
    for (unsigned int i = 0; i < vector_1.size(); i++)
        std::cout << " " << vector_1[i];
    std::cout << "\n";

    // using std::equal()
    // Comparison based on pred
    if ( std::equal (vector_1.begin(), vector_1.end(), v1, pred) )
        std::cout << "The contents of both sequences are equal.\n";
    else
        printf("The contents of both sequences differ.");

}
```

**输出:**

```cpp
Vector contains :  10, 20, 30, 40, 50
The contents of both sequences differ.
```

## 相关文章:

*   [std::max_element](https://www.geeksforgeeks.org/stdmax_element-in-cpp/)
*   [std::max](https://www.geeksforgeeks.org/stdmax-in-cpp/)
*   [std::min](https://www.geeksforgeeks.org/stdmin-in-cpp/)
*   [std::min_element in C++](https://www.geeksforgeeks.org/stdmin_element-in-cpp/)

本文由 **Mohit Gupta_OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。