# STD::c++ 中的 find _ end

> 原文:[https://www.geeksforgeeks.org/stdfind_end-in-cpp/](https://www.geeksforgeeks.org/stdfind_end-in-cpp/)

**std::find_end** 用于查找容器内子序列的最后一次出现。它在范围[first1，last1]中搜索由[first2，last2 定义的序列的最后一次出现，并返回一个迭代器到它的第一个元素，如果没有发现出现，则返回 last 1。

它类似于**[【std::search】](https://www.geeksforgeeks.org/stdsearch-in-c/)**，在 STD::search 中，我们在另一个容器中寻找一个子序列的**第一个**出现，而在 **std::find_end** 中，我们寻找这个子序列的**最后一个**出现，如果找到了这个子序列，就返回一个迭代器到第一个元素。

它有两种使用方式，如下所示:

1.  **使用==:** 比较元素

语法:

```cpp
Template
   ForwardIterator1 find_end (ForwardIterator1 first1, ForwardIterator1 last1,
                              ForwardIterator2 first2, ForwardIterator2 last2);

first1: Forward iterator to the first element in the first range.
last1: Forward iterator to the last element in the first range.
first2: Forward iterator to the first element in the second range.
last2: Forward iterator to the last element in the second range.

Return Value: It returns an iterator to the first element of 
the last occurrence of [first2,last2) in [first1,last1).
If the sequence is not found or [first2,last2) is empty,
the function returns last1.

```

```cpp
// C++ program to demonstrate the use of std::find_end
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;
int main()
{
    // Defining first container
    vector<int>v = {1, 3, 10, 3, 10, 1, 3, 3, 10, 7, 8, 
                    1, 3, 10};

    // Defining second container
    vector<int>v1 = {1, 3, 10};

    vector<int>::iterator ip;

    // Using std::find_end
    ip = std::find_end(v.begin(), v.end(), v1.begin(),
                       v1.end());

    // Displaying the index where the last common occurrence 
    // begins
    cout << (ip - v.begin()) << "\n";
    return 0;
}
```

输出:

```cpp
11

```

*   **By comparing using a pre-defined function:**

    语法:

    ```cpp
    Template
       ForwardIterator1 find_end (ForwardIterator1 first1, ForwardIterator1 last1,
                                  ForwardIterator2 first2, ForwardIterator2 last2,
                                  BinaryPredicate pred);

    Here, first1, last1, first2, and last2 are
    the same as the previous case.

    Pred: Binary function that accepts two elements
    as arguments (one of each of the two sequences, in the same order),
    and returns a value convertible to bool. 
    The value returned indicates whether the elements are considered
    to match in the context of this function.
    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Return Value: It returns an iterator to the first element of
    the last occurrence of [first2,last2) in [first1,last1).
    If the sequence is not found or [first2,last2) is empty, 
    the function returns last1.
    ```

    ```cpp
    // C++ program to demonstrate the use of std::find_end
    #include<iostream>
    #include<vector>
    #include<algorithm>
    using namespace std;

    // Defining the BinaryFunction
    bool Pred (int a, int b)
    {
        return (a == b);
    }
    int main()
    {
        // Defining first container
        vector<int>v = {1, 5, 7, 11, 13, 15, 30, 30, 7} , i;

        // Defining second container
        vector<int>v1 = {13, 15};

        vector<int>::iterator ip;

        // Using std::find_end
        ip = std::find_end(v.begin(), v.end(), v1.begin(), 
                           v1.end(), Pred);

        // Displaying the index where the last common occurrence
        // begins
        cout << (ip - v.begin()) << "\n";

        return 0;
    }
    ```

    输出:

    ```cpp
    4

    ```

    **哪里可以用？**

    1.  **To search from the end:** It is the reverse variant of **std::search**, i.e., std::search searches for a sub-sequence from the beginning of the list , such that it can return the first occurrence of that subsequence.

        另一方面 **std::find_end** 如果我们想从列表的末尾搜索一个子序列，可以使用，这个子序列将自动成为容器内任何子序列的最后一个出现。
        (如果你在想为什么叫 std::find_end 而不是 std::search_end，那就不是你一个人了！！！)

        所以，如果必须从头开始搜索的话，这是 std::search 的一个**可能的替代。**

        ```cpp
        // C++ program to demonstrate the use of std::find_end

        #include <iostream>
        #include <vector>
        #include <algorithm>
        using namespace std;
        int main()
        {
            int i, j;

            // Declaring the sequence to be searched into
            vector<int> v1 = { 1, 2, 3, 4, 5, 6, 7, 3, 4, 5 };

            // Declaring the subsequence to be searched for
            vector<int> v2 = {3, 4};

            // Declaring an iterator for storing the returning pointer
            vector<int>::iterator i1;

            // Using std::search to find the first occurrence of v2
            i1 = std::search(v1.begin(), v1.end(), v2.begin(), 
                             v2.end());

            // checking if iterator i1 contains end pointer of v1 or
            // not
            if (i1 != v1.end()) {
                cout << "vector2 is present firstly at index " 
                     << (i1 - v1.begin());
            } else {
                cout << "vector2 is not present in vector1";
            }

            // Using std::find_end to find the last occurrence of v2
            i1 = std::find_end(v1.begin(), v1.end(), v2.begin(), 
                               v2.end());

            // checking if iterator i1 contains end pointer of v1 or 
            //not
            if (i1 != v1.end()) {
                cout << "\nvector2 is present lastly at index " 
                     << (i1 - v1.begin());
            } else {
                cout << "vector2 is not present in vector1";
            }
            return 0;
        }
        ```

        输出:

        ```cpp
        vector2 is present firstly at index 2
        vector2 is present lastly at index 7

        ```

    2.  **To find last occurrence of element satisfying a condition:** Since, **std::find_end** starts searching from the end, so we can use this fact as well as manipulate the BinaryFunction to solve questions which demand us to **find the last occurrence of anything** (like last odd number, last even number, and so on).

        ```cpp
        // C++ program to find the last occurrence of an odd
        // and even number
        #include<iostream>
        #include<vector>
        #include<algorithm>
        using namespace std;

        // Defining the Predicate Function to find the last occurrence
        // of an odd number
        bool pred( int a, int b)
        {
            if (a % b != 0) {
                return 1;
            } else {
                return 0;
            }
        }

        // Defining the Predicate Function to find the last occurrence
        // of an even number
        bool pred1( int a, int b)
        {
            if (a % b == 0) {
                return 1;
            } else {
                return 0;
            }
        }

        int main()
        {

            // Defining a vector
            vector<int>v1 = {1, 3, 4, 5, 6, 7, 8, 10};

            // Declaring a sub-sequence
            vector<int>v2 = {2};

            // Using std::find_end to find the last occurrence of an
            // odd number
            vector<int>::iterator ip;
            ip = std::find_end(v1.begin(), v1.end(), v2.begin(),
                               v2.end(), pred);

            // Displaying the index where the last odd number occurred
            cout << "Last odd no. occurs at " <<  (ip - v1.begin());

            // Using std::find_end to find the last occurrence of an 
            // even number
            ip = std::find_end(v1.begin(), v1.end(), v2.begin(),
                               v2.end(), pred1);

            // Displaying the index where the last even number occurred
            cout << "\nLast even no. occurs at " <<  (ip - v1.begin());

            return 0;
        }
        ```

        输出:

        ```cpp
        Last odd no. occurs at 5
        Last even no. occurs at 7

        ```

        **代码说明:**这里，我们对 Binary Function 进行了操作，使得它搜索第一个容器中的元素是否是第二个容器中元素的倍数，在第二个容器中我们存储了 2，因此借助于此，我们能够找到奇数或偶数的最后一次出现。

**相关文章:**

*   [标准::搜索](https://www.geeksforgeeks.org/stdsearch-in-c/)
*   [标准::查找](https://www.geeksforgeeks.org/stdfind-in-c/)
*   [std::find_if，std::find_if_not](https://www.geeksforgeeks.org/stdfind_if-stdfind_if_not-in-c/)
*   [标准::第 n _ 元素](https://www.geeksforgeeks.org/stdnth_element-in-cpp/)

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。