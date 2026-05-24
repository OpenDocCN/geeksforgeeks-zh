# std::相邻 _ c++ 中的差异

> 原文:[https://www . geesforgeks . org/STD-相邻 _ CPP 差异/](https://www.geeksforgeeks.org/std-adjacent_difference-in-cpp/)

**计算范围的相邻差**
为从结果开始的范围中的每个元素分配范围[第一个，最后一个]中其对应元素与其前一个元素之间的差(除了*result，它被分配为*first)。

如果 x 代表[第一个，最后一个]中的元素，y 代表结果中的元素，则 ys 可以计算为:

```cpp
y0 = x0
y1 = x1 - x0
y2 = x2 - x1
y3 = x3 - x2
y4 = x4 - x3
and so on.
```

1.**使用默认版本:**
语法:
**模板:**

```cpp
OutputIterator adjacent_difference (InputIterator first,
                                    InputIteratorlast,
                                    OutputIterator result);
Parameters :

first, last
Input iterators to the initial and final positions in a sequence.
The range used is [first, last], which contains all the elements
between first and last, including the element pointed by first but
not the element pointed by last.

result
Output iterator to the initial position in the destination sequence
where the differences are stored. The range starts at result and
shall have a size large enough to contain as many elements as the
range above [first, last]. 

Return Type :
An iterator pointing to past the last element of the destination
sequence where resulting elements have been stored.

```

```cpp
// CPP program to illustrate
// std :: adjacent_difference

#include <iostream> // std::cout
#include <numeric> // std::adjacent_difference

// Driver code
int main()
{
    int val[] = { 1, 2, 3, 5, 9, 11, 12 };
    int n = sizeof(val) / sizeof(val[0]);
    int result[7];

    // Array contains
    std::cout << "Array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << val[i];
    std::cout << "\n";

    // Using default std :: adjacent_difference
    std::adjacent_difference(val, val + 7, result);
    std::cout << "Using default adjacent_difference: ";
    for (int i = 1; i < n; i++)
        std::cout << result[i] << ' ';
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
Array contains : 1 2 3 5 9 11 12
Using default adjacent_difference: 1 1 2 4 2 1

```

2.**使用自定义版本，以功能为 comp**
语法:
**模板:**

```cpp
OutputIterator adjacent_difference (InputIterator first,
                                    InputIterator last,
                                    OutputIterator result,
                                    BinaryOperation binary_op);

Parameters :

first, last, result are same as above.

binary_op
Binary operation taking as arguments two elements of the type
pointed by InputIterator, and returning the result of the
replacement for the difference operation.
This can either be a function pointer or a function object. 

Return Type :
An iterator pointing to past the last element of the destination
sequence where resulting elements have been stored.

```

通过在自定义函数中将运算符**更改为任意二进制运算符**，我们可以更改应用于 STL 函数的操作。这里执行相邻元素的求和。

```cpp
// CPP program to illustrate
// std :: adjacent_difference

#include <iostream> // std::cout
#include <numeric> // std::adjacent_difference

int comp(int x, int y)
{
    return x + y;
}

// Driver code
int main()
{
    int val[] = { 1, 2, 3, 5, 9, 11, 12 };
    int n = sizeof(val) / sizeof(val[0]);
    int result[7];

    // Array contains
    std::cout << "Array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << val[i];
    std::cout << "\n";

    // std :: adjacent_difference using custom function
    std::adjacent_difference(val, val + 7, result, comp);

    std::cout << "Using custom function: ";
    for (int i = 0; i < n; i++)
        std::cout << result[i] << ' ';
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
Array contains : 1 2 3 5 9 11 12
Using custom function: 1 3 5 8 14 20 23 

```

**实际应用:**在所述范围的相邻元素之间执行任何二进制运算(范围的第一个元素除外)。

1.求数组中相邻元素的乘积。
例如，数组包含:2 4 5 6
结果为:2 8 20 30
解释–第一个元素保持原样。那么第二个元素就是第一个元素*第二个元素，然后第三个元素就是第二个元素*第三个元素，以此类推。

```cpp
// CPP program to illustrate
// std :: adjacent_difference

#include <iostream> // std::cout
#include <numeric> // std::adjacent_difference

int comp(int x, int y)
{
    return x * y;
}

// Driver code
int main()
{
    int val[] = { 5, 7, 4, 8, 2 };
    int n = sizeof(val) / sizeof(val[0]);
    int result[n];

    // Array contains
    std::cout << "Array contains :";
    for (int i = 0; i < n; i++)
        std::cout << " " << val[i];
    std::cout << "\n";

    // Using custom std :: adjacent_difference
    std::adjacent_difference(val, val + 7, result, comp);
    std::cout << "Result contains :";
    for (int i = 0; i < n; i++)
        std::cout << ' ' << result[i];
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
Array contains : 5 7 4 8 2
Result contains : 5 35 28 32 16

```

本文由**沙钦·毕斯特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。