# std::search_n 用 C++ 举例

> 原文:[https://www . geesforgeks . org/stdsearch _ n-with-example-in-CPP/](https://www.geeksforgeeks.org/stdsearch_n-with-example-in-cpp/)

先决条件:[STD::search](https://www.geeksforgeeks.org/stdsearch-in-c/)
**STD::search _ n**是头文件中定义的 STL 算法，用于搜索给定元素是否与容器元素连续满足给定次数的谓词(如果未定义此类谓词，则等于)。

它在**范围【第一个，最后一个】**中搜索计数元素序列，每个计数元素都等于给定值(版本 1)或满足谓词(版本 2)。

如果没有找到这样的序列，这个函数返回一个迭代器到第一个这样的元素，或者一个迭代器到容器的最后一个元素。

**STD::search _ n 的两个版本定义如下–**

1.  **For comparing elements using ==:**

    语法:

    ```cpp
     ForwardIterator search_n (ForwardIterator first, ForwardIterator last,
                               Size count, const T& val);

    first: 
    Forward iterator to beginning of the container to be searched into.
    last: 
    Forward iterator to end of the container to be searched into.
    count: 
    Minimum number of successive elements to match.
    Size shall be (convertible to) an integral type.
    val: Individual value to be compared.
    Returns: 
    It returns an iterator to the first element of the sequence.
    If no such sequence is found, the function returns last.

    ```

    ```cpp
    // C++ program to demonstrate the use of std::search_n

    #include <iostream>
    #include <vector>
    #include <algorithm>
    using namespace std;
    int main()
    {
        int i, j;

        // Declaring the sequence to be searched into
        vector<int> v1 = { 1, 2, 3, 4, 5, 3, 3, 6, 7 };

        // Declaring the value to be searched for
        int v2 = 3;

        // Declaring an iterator for storing the returning pointer
        vector<int>::iterator i1;

        // Using std::search_n and storing the result in
        // iterator i1
        i1 = std::search_n(v1.begin(), v1.end(), 2, v2);

        // checking if iterator i1 contains end pointer of v1 or not
        if (i1 != v1.end()) {
            cout << "v2 is present consecutively 2 times at index "
                 << (i1 - v1.begin());
        } else {
            cout << "v2 is not present consecutively 2 times in "
                 << "vector v1";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    v2 is present consecutively 2 times at index 5

    ```

2.  **For comparing element using a predicate:**
    Syntax:

    ```cpp
    ForwardIterator search_n ( ForwardIterator first, ForwardIterator last,
                               Size count, const T& val, BinaryPredicate pred );

    All the arguments are same as previous template, just one more argument is added

    pred: Binary function that accepts two arguments 
    (one element from the sequence as first, and val as second),
     and returns a value convertible to bool. The value returned indicates whether 
    the element is considered a match in the context of this function.
    The function shall not modify any of its arguments. 
    This can either be a function pointer or a function object.

    Returns:
    It also returns value as per the previous version, i.e., 
    an iterator to the first element of the sequence, 
    satisfying a condition with respect to a given value.
    If no such sequence is found, the function returns last.
    ```

    ```cpp
    // C++ program to demonstrate the use of std::search_n
    // with binary predicate
    #include <iostream>
    #include <vector>
    #include <algorithm>
    using namespace std;

    // Defining the BinaryPredicate function
    bool pred(int i, int j)
    {
        if (i == j) {
            return 1;
        } else {
            return 0;
        }
    }

    int main()
    {
        int i, j;

        // Declaring the sequence to be searched into
        vector<int> v1 = { 1, 2, 3, 4, 5, 3, 3, 6, 7 };

        // Declaring the value to be compared to v1 based
        // on a given predicate
        int v2 = 3;

        // Declaring an iterator for storing the returning pointer
        vector<int>::iterator i1;

        // Using std::search_n and storing the result in
        // iterator i1
        i1 = std::search_n(v1.begin(), v1.end(), 2, v2, pred);

        // checking if iterator i1 contains end pointer of v1 or not
        if (i1 != v1.end()) {
            cout << "v2 is present consecutively 2 times at index "
                 << (i1 - v1.begin());
        } else {
            cout << "v2 is not present consecutively 2 times "
                 << "in vector v1";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    v2 is present consecutively 2 times at index 5

    ```

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。