# std::set_difference in C++

> 原文:[https://www.geeksforgeeks.org/std-set_difference-in-cpp/](https://www.geeksforgeeks.org/std-set_difference-in-cpp/)

两个集合的差异是由第一个集合中的元素形成的，而不是第二个集合中的元素。函数复制的元素总是以相同的顺序来自第一个范围。
两个范围内的元素应已订购。

1.**使用“<”比较元素:**
语法:

```cpp
Template :
OutputIterator set_difference (InputIterator1 first1, InputIterator1 last1,
                               InputIterator2 first2, InputIterator2 last2,
                               OutputIterator result);

Parameters :

first1, last1
Input iterators to the initial and final positions of the first
sorted sequence. The range used is [first1, last1), which contains
all the elements between first1 and last1, including the element
pointed by first1 but not the element pointed by last1.
first2, last2
Input iterators to the initial and final positions of the second
sorted sequence. The range used is [first2, last2).

result
Output iterator to the initial position of the range where the
resulting sequence is stored.
The pointed type shall support being assigned the value of an
element from the first range.

Return Type :
An iterator to the end of the constructed range.

```

```cpp
// CPP program to illustrate
// std :: set_difference

#include <bits/stdc++.h>

int main()
{
    int first[] = { 5, 10, 15, 20, 25 };
    int second[] = { 50, 40, 30, 20, 10 };
    int n = sizeof(first) / sizeof(first[0]);

    std::vector<int> v2(5);
    std::vector<int>::iterator it, ls;

    std::sort(first, first + 5);
    std::sort(second, second + 5);

    // Print elements
    std::cout << "First array :";
    for (int i = 0; i < n; i++)
        std::cout << " " << first[i];
    std::cout << "\n";

    // Print elements
    std::cout << "Second array :";
    for (int i = 0; i < n; i++)
        std::cout << " " << second[i];
    std::cout << "\n\n";

    // using default comparison
    /* first array intersection second array */
    ls = std::set_difference(first, first + 5, second, second + 5, v2.begin());

    std::cout << "Using default comparison, \n";
    std::cout << "The difference has " << (ls - v2.begin()) << " elements :";
    for (it = v2.begin(); it < ls; ++ it)
        std::cout << " " << *it;
    std::cout << "\n";

    return 0;
}
```

输出:

```cpp
First array : 5 10 15 20 25
Second array : 10 20 30 40 50

Using default comparison,
The difference has 3 elements : 5 15 25

```

2.**通过使用预定义函数进行比较:**

```cpp
Template :
OutputIterator set_difference (InputIterator1 first1, InputIterator1 last1,
                               InputIterator2 first2, InputIterator2 last2,
                               OutputIterator result, Compare comp);

Parameters :

first1, last1, first2, last2, result are same as above.

comp
Binary function that accepts two arguments of the types pointed
by the input iterators, and returns a value convertible to bool.
The function shall not modify any of its arguments.
This can either be a function pointer or a function object.

Return Type :
An iterator to the end of the constructed range.

```

```cpp
// CPP program to illustrate
// std :: set_difference

#include <bits/stdc++.h>

bool comp(int i, int j)
{
    return (i < j);
}

int main()
{
    int first[] = { 50, 40, 30, 20, 10 };
    int second[] = { 5, 10, 15, 20, 25 };
    int n = sizeof(first) / sizeof(first[0]);

    std::vector<int> v1(5);

    std::sort(first, first + 5);
    std::sort(second, second + 5);

    // Print elements
    std::cout << "First array :";
    for (int i = 0; i < n; i++)
        std::cout << " " << first[i];
    std::cout << "\n";

    // Print elements
    std::cout << "Second array :";
    for (int i = 0; i < n; i++)
        std::cout << " " << second[i];
    std::cout << "\n\n";

    // using custom comparison, function as comp
    /* first array intersection second array */
    ls = std::set_difference(second, second + 5, first, first + 5, v1.begin(), comp);

    std::cout << "Using custom comparison, \n";
    std::cout << "The difference has " << (ls - v1.begin()) << " elements :";
    for (it = v1.begin(); it < ls; ++ it)
        std::cout << " " << *it;
    std::cout << "\n";

    return 0;
}
```

输出:

```cpp
First array : 10 20 30 40 50
Second array : 5 10 15 20 25

Using custom comparison :
The difference has 3 elements : 30 40 50

```

**可能的应用:**用于查找只出现在第一个列表中而不出现在第二个列表中的元素。

1.可以用来查找只上第一节课的**学生名单。**

```cpp
// CPP program to demonstrate use of
// std :: set_difference
#include <iostream>
#include <algorithm>
#include <vector>
#include <string>

using namespace std;

// Driver code
int main()
{
    string first[] = { "Sachin", "Rakesh", "Sandeep", "Serena" };
    string second[] = { "Vaibhav", "Sandeep", "Rakesh", "Neha" };
    int n = sizeof(first) / sizeof(first[0]);

    // Print students of first list
    cout << "Students in first class :";
    for (int i = 0; i < n; i++)
        cout << " " << first[i];
    cout << "\n";

    // Print students of second list
    cout << "Students in second class :";
    for (int i = 0; i < n; i++)
        cout << " " << second[i];
    cout << "\n\n";

    vector<string> v(10);
    vector<string>::iterator it, st;

    // Sorting both the list
    sort(first, first + n);
    sort(second, second + n);

    // Using default operator<
    it = set_difference(first, first + n, second, second + n, v.begin());

    cout << "Students attending first class only are :\n";
    for (st = v.begin(); st != it; ++ st)
        cout << ' ' << *st;
    cout << '\n';

    return 0;
}
```

**输出:**

```cpp
Students in first class : Sachin Rakesh Sandeep Serena
Students in second class : Vaibhav Sandeep Rakesh Neha

Students attending first classe only are :
 Sachin Serena

```

2.它也可以用来**找到第一个列表中没有的元素。**
程序如上。

本文由 **[沙钦·毕斯特](https://www.linkedin.com/in/sachin-bisht-984b5013a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。