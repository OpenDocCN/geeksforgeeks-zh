# c++ STL 中的无序 _ 集合 end()

> 原文:[https://www.geeksforgeeks.org/unordered_set-end-in-c-stl/](https://www.geeksforgeeks.org/unordered_set-end-in-c-stl/)

unordered_set::end()函数是 C++ STL 中的一个内置函数，它返回一个指向结束元素的迭代器。这个迭代器并不直接指向一个元素，而是指向最后一个元素之后的位置。

**语法**

```cpp
umap_name.end()

or,

umap_name.end(int i)

```

**参数**:本功能取单个整数参数![i](img/2c0fdcc58b35808b7d0c28592907fe1a.png "Rendered by QuickLaTeX.com")，可选。

**返回值**:

*   如果参数![i](img/2c0fdcc58b35808b7d0c28592907fe1a.png "Rendered by QuickLaTeX.com")没有被传递，那么函数返回一个指向结束元素的迭代器。实际上，它并不指向集合中的任何元素，而是指向容器最后一个元素之后的位置。
*   如果参数![i](img/2c0fdcc58b35808b7d0c28592907fe1a.png "Rendered by QuickLaTeX.com")被传递，那么函数返回一个迭代器，指向第 I 个桶的结束元素。与前面的情况一样，它不指向集合中的任何元素，而是指向第 I 个桶的最后一个元素之后的位置。
    所以 unordered_set::end()返回的迭代器不能解引用。

下面的程序说明了无序集::end()函数:

**程序 1:**

```cpp
// CPP program to illustrate the unordered_set::end() 
// function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    unordered_set<int> sampleSet = 
            { 5, 10, 15, 4, 2, 7, 8, 6 };

    // Continue the loop until it points to the
    // past-the-end position returned by sampleSet.end()
    for (auto it = sampleSet.begin(); it != sampleSet.end(); 
                                                        it++) 
    {
        cout << *it << " ";
    }

    return 0;
}
```

**Output:**

```cpp
6 8 7 2 4 15 10 5

```

**程序 2** :

```cpp
// CPP program to illustrate the
// unordered_set::end() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    unordered_set<int> sampleSet = 
                { 5, 10, 15, 4, 2, 7, 8, 6 };

    // displaying all the buckets of the set.
    // Continue the loop until it points to the 
    // past-the-end position returned by sampleset.end(i)
    for (unsigned i = 0; i < sampleSet.bucket_count(); ++ i) 
    {
        cout << "Bucket " << i << " Contains: ";
        for (auto it1 = sampleSet.begin(i); 
                        it1 != sampleSet.end(i); ++ it1)
            cout << " " << *it1;
        cout << endl;
    }

    return 0;
}
```

**Output:**

```cpp
Bucket 0 Contains: 
Bucket 1 Contains: 
Bucket 2 Contains:  2
Bucket 3 Contains: 
Bucket 4 Contains:  4 15
Bucket 5 Contains:  5
Bucket 6 Contains:  6
Bucket 7 Contains:  7
Bucket 8 Contains:  8
Bucket 9 Contains: 
Bucket 10 Contains:  10

```