# 使用 STL |集合 1(使用集合)

计算唯一三角形的数量

> 原文:[https://www . geesforgeks . org/count-number-of-unique-triangles-using-STL/](https://www.geeksforgeeks.org/count-number-of-unique-triangles-using-stl/)

我们给定 n 个三角形，它们的三条边的长度分别是 a，b，c。现在我们需要计算这 n 个三角形中唯一三角形的数量。如果两个三角形至少有一条边不同，那么它们就是不同的。

示例:

```cpp
Input: arr[] = {{1, 2, 2},
                {4, 5, 6}, 
                {4, 5, 6}    
Output: 2

Input: arr[] = {{4, 5, 6}, {6, 5, 4},
                {1, 2, 2}, {8, 9, 12}
Output: 3
```

**我们强烈建议你尽量减少浏览器，先自己试试这个。**

既然要求我们找到“唯一”三角形的数量，我们可以使用[集合](http://geeksquiz.com/set-associative-containers-the-c-standard-template-library-stl/)或者无序 _ 集合。本文讨论了基于集合的方法。

如何将三面作为一个元素存储在容器中？我们使用 STL [对](http://geeksquiz.com/pair-simple-containers-the-c-standard-template-library-stl/)将所有三个面存储在一起作为

```cpp
pair <int, pair<int, int> >
```

我们一个接一个地将所有三角形插入集合中。但是这种方法的问题是，边为{4，5，6}的三角形与边为{5，4，6}的三角形不同，尽管它们指的是同一个三角形。

为了处理这种情况，我们以排序的顺序存储边(基于边的长度)，这里排序不会成为问题，因为我们只有 3 个边，并且我们可以在恒定的时间内对它们进行排序。例如，将{5，4，6}插入集合{4，5，6}

注意:我们可以通过 make_pair(a，b)进行配对，也可以简单地使用{a，b}。

下面是上面思路的 C++ 实现:

```cpp
// A C++ program to find number of unique Triangles
#include <bits/stdc++.h>
using namespace std;

// Creating shortcut for an integer pair.
typedef pair<int, int> iPair;

// A structure to represent a Triangle with
// three sides as a, b, c
struct Triangle
{
    int a, b, c;
};

// A function to sort three numbers a, b and c.
// This function makes 'a' smallest, 'b' middle
// and 'c' largest (Note that a, b and c are passed
// by reference)
int sort3(int &a, int &b, int &c)
{
    vector<int> arr({a, b, c});
    sort(arr.begin(), arr.end());
    a = arr[0]; b = arr[1]; c = arr[2];
}

// Function returns the number of unique Triangles
int countUniqueTriangles(struct Triangle arr[],
                           int n)
{
    // A set which consists of unique Triangles
    set < pair< int, iPair > > s;

    // Insert all triangles one by one
    for (int i=0; i<n; i++)
    {
        // Find three sides and sort them
        int a = arr[i].a, b = arr[i].b, c = arr[i].c;
        sort3(a, b, c);

        // Insert a triangle into the set
        s.insert({a, {b, c}});
    }

    // Return set size
    return s.size();
}

// Driver program to test above function
int main()
{
    // An array of structure to store sides of 6 Triangles
    struct Triangle arr[] = {{3, 2, 2}, {3, 4, 5}, {1, 2, 2},
                             {2, 2, 3}, {5, 4, 3}, {6, 4, 5}};
    int n = sizeof(arr)/sizeof(Triangle);

    cout << "Number of Unique Triangles are "
         << countUniqueTriangles(arr, n);
    return 0;
}
```

输出:

```cpp
Number of Unique Triangles are 4
```

上述解决方案的时间复杂度为 0(n Log n)，因为集合需要 0(Log n)的插入时间。

我们可以使用[无序集](https://www.geeksforgeeks.org/unorderd_set-stl-uses/)将时间复杂度提高到 O(n)。但是使用无序集需要编写一个散列函数，因为散列函数没有在成对库中定义。

相关文章:[可能的三角形数量](https://www.geeksforgeeks.org/find-number-of-triangles-possible/)

本文由 **Chirag Agrawal** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论