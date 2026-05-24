# std::在 C++ 中搜索

> 原文:[https://www.geeksforgeeks.org/stdsearch-in-c/](https://www.geeksforgeeks.org/stdsearch-in-c/)

**std::search** 在头文件<算法>中定义，用于找出满足关于另一个序列的条件(如果没有定义这样的谓词，等于)的子序列的存在。

*   它在序列[first1，last1)中搜索由[first2，last2 定义的子序列的第一个匹配项，并返回一个迭代器到它的第一个匹配项元素，如果没有找到匹配项，则返回 last1。
*   它使用运算符==(版本 1)或基于任何给定的谓词(版本 2)顺序比较两个范围中的元素。[first1，last1 的子序列只有在[first2，last2 的所有元素都匹配时才被视为匹配。最后，std::search 返回第一个这样的事件。

**两个版本都可以使用，如下图:**

1.  **使用== :**
    比较元素

> **ForwardIterator1 搜索(ForwardIterator1 first1，ForwardIterator1 last1，**
> **forward iterator 2 first 2，forward iterator 2 last 2)；**
> **first1:**
> 向前迭代器，到达要搜索的第一个容器的开头。
> **last1:**
> 向前迭代器到要搜索的第一个容器的末尾。
> **first2:**
> 向前迭代器到要搜索的第二个容器的子序列的开头。
> **last2:**
> 前向迭代器到要搜索的第二个容器的子序列的结尾。
> **返回:**f 的第一个元素的迭代器
> 第一次出现[first1，last 1]中的[first2，last2，如果没有发现出现，则返回 last1
> 。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate the use of std::search

#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    int i, j;

    // Declaring the sequence to be searched into
    vector<int> v1 = { 1, 2, 3, 4, 5, 6, 7 };

    // Declaring the subsequence to be searched for
    vector<int> v2 = { 3, 4, 5 };

    // Declaring an iterator for storing the returning pointer
    vector<int>::iterator i1;

    // Using std::search and storing the result in
    // iterator i1
    i1 = std::search(v1.begin(), v1.end(), v2.begin(), v2.end());

    // checking if iterator i1 contains end pointer of v1 or not
    if (i1 != v1.end()) {
        cout << "vector2 is present at index " << (i1 - v1.begin());
    } else {
        cout << "vector2 is not present in vector1";
    }

    return 0;
}
```

1.  输出:

```cpp
vector2 is present at index 2
```

2.  **用于基于谓词(或条件)的比较:**

> **ForwardIterator1 搜索(ForwardIterator1 first1，ForwardIterator1 last1，**
> **forwarditerator 2 first 2，ForwardIterator2 last2，**
> **binary redirecate pred)；**
> 所有的参数都和之前的模板一样，只是多加了一个参数
> **pred:** Binary 函数接受两个元素作为参数(两个容器各一个，顺序相同)，返回一个可转换为 bool 的值。返回值指示在此函数的上下文中是否认为元素匹配。该函数不得修改其任何参数。这可以是函数指针，也可以是函数对象。
> **返回:**一个迭代器，返回满足谓词的[first2，last2 的第一个出现的第一个元素，在[first1，last1]中，如果没有发现出现，则返回 last 1。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate the use of std::search
// with binary predicate
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

// Defining the BinaryPredicate function
bool pred(int i, int j)
{
    if (i > j) {
        return 1;
    } else {
        return 0;
    }
}

int main()
{
    int i, j;

    // Declaring the sequence to be searched into
    vector<int> v1 = { 1, 2, 3, 4, 5, 6, 7 };

    // Declaring the subsequence to be compared to based
    // on predicate
    vector<int> v2 = { 3, 4, 5 };

    // Declaring an iterator for storing the returning pointer
    vector<int>::iterator i1;

    // Using std::search and storing the result in
    // iterator i1 based on predicate pred
    i1 = std::search(v1.begin(), v1.end(), v2.begin(), v2.end(), pred);

    // checking if iterator i1 contains end pointer of v1 or not
    if (i1 != v1.end()) {
        cout << "vector1 elements are greater than vector2 starting "
             << "from position " << (i1 - v1.begin());
    } else {
        cout << "vector1 elements are not greater than vector2 "
             << "elements consecutively.";
    }

    return 0;
}
```

1.  输出:

```cpp
vector1 elements are greater than vector2 starting from position 3
```

**相关文章:**

*   [std::search_n](https://www.geeksforgeeks.org/stdsearch_n-with-example-in-cpp/)
*   [标准::查找](https://www.geeksforgeeks.org/stdfind-in-c/)
*   [std::find_if，std::find_if_not](https://www.geeksforgeeks.org/stdfind_if-stdfind_if_not-in-c/)
*   [标准::第 n _ 元素](https://www.geeksforgeeks.org/stdnth_element-in-cpp/)
*   [std::find_end](https://www.geeksforgeeks.org/stdfind_end-in-cpp/)

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。