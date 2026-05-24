# 标准::C++ 中的 set _ 交集

> 原文:[https://www.geeksforgeeks.org/std-set_intersection-in-cpp/](https://www.geeksforgeeks.org/std-set_intersection-in-cpp/)

两个集合的交集仅由两个集合中存在的元素构成。函数复制的元素总是以相同的顺序来自第一个范围。两个范围内的元素都应已订购。

**示例:**

```cpp
Input :
5 10 15 20 25
50 40 30 20 10

Output :
The intersection has 2 elements :
10 20 

```

1.**使用“<”比较元素:**
语法:

```cpp
Template :
OutputIterator set_intersection (InputIterator1 first1, InputIterator1 last1,
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
// std :: set_intersection

#include <bits/stdc++.h>

int main()
{
    int first[] = { 5, 10, 15, 20, 25 };
    int second[] = { 50, 40, 30, 20, 10 };
    int n = sizeof(first) / sizeof(first[0]);

    std::vector<int> v1(5);
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

    // std :: set_intersection
    ls = std::set_intersection(first, first + 5, second, second + 5, v1.begin());

    std::cout << "The intersection has " << (ls - v1.begin()) << " elements:";
    for (it = v1.begin(); it != ls; ++ it)
        std::cout << ' ' << *it;
    std::cout << "\n";

    return 0;
}
```

输出:

```cpp
First array : 5 10 15 20 25
Second array : 10 20 30 40 50

The intersection has 2 elements: 10 20

```

2.**通过使用预定义函数进行比较:**
Synatax:

```cpp
Template :
OutputIterator set_intersection (InputIterator1 first1, InputIterator1 last1,
                                 InputIterator2 first2, InputIterator2 last2,
                                 OutputIterator result, Compare comp);

Parameters :

first1, last1, first2, last2, result are same as mentioned above.

comp
Binary function that accepts two arguments of the types pointed
by the input iterators, and returns a value convertible to bool.
The function shall not modify any of its arguments.
This can either be a function pointer or a function object.
It follows the strict weak ordering to order the elements.

Return Type :
An iterator to the end of the constructed range.

```

```cpp
// CPP program to illustrate
// std :: set_intersection

#include <bits/stdc++.h>

bool comp(int a, int b)
{
    return a < b;
}

int main()
{
    int first[] = { 5, 10, 15, 20, 25 };
    int second[] = { 50, 40, 30, 20, 10 };
    int n = sizeof(first) / sizeof(first[0]);

    std::vector<int> v1(5);
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

    // std :: set_intersection
    ls = std::set_intersection(first, first + 5, second, second + 5, v1.begin(), comp);

    std::cout << "The intersection has " << (ls - v1.begin()) << " elements:";
    for (it = v1.begin(); it != ls; ++ it)
        std::cout << ' ' << *it;
    std::cout << "\n";

    return 0;
}
```

输出:

```cpp
First array : 5 10 15 20 25
Second array : 10 20 30 40 50
The intersection has 2 elements: 10 20

```

**可能的应用:**用于查找只存在于两个集合中的元素。

1.它可以用来**找到两个班级的学生名单。**

```cpp
// CPP program to demonstrate use of
// std :: set_intersection
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
    it = set_intersection(first, first + n, second, second + n, v.begin());

    cout << "Students attending both the classes only are :\n";
    for (st = v.begin(); st != it; ++ st)
        cout << ' ' << *st;
    cout << '\n';

    return 0;
}
```

输出:

```cpp
Students in first class : Sachin Rakesh Sandeep Serena
Students in second class : Vaibhav Sandeep Rakesh Neha

Students attending both classes only are :
 Rakesh Sandeep

```

2.也可以用来**查找两个列表中的共同元素。**
程序如上。
3。复杂性
复杂性在[第一个 1，最后一个 1]和[第一个 2，最后一个 2]之间的距离是线性的:执行高达
2*(计数 1+计数 2)-1 的比较。其中 count1 = last1- first1，count2 = last2- first2。
本文由 **[萨钦毕斯特](https://www.linkedin.com/in/sachin-bisht-984b5013a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。