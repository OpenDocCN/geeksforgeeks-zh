# std::find_first_of 在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdfind_first_of-in-cpp/](https://www.geeksforgeeks.org/stdfind_first_of-in-cpp/)

**std::find_first_of** 用于比较两个容器之间的元素。它将范围[first1，last1 中的所有元素与范围[first2，last2 中的元素进行比较，如果在第一个范围中找到第二个范围中的任何元素，那么它将返回该元素的迭代器。

如果两个范围中有多个公共元素，那么返回第一个容器中第一个公共元素的迭代器。如果没有匹配，则返回指向 last1 的迭代器。

它有两种使用方式，如下所示:

1.  **使用==:** 比较元素

语法:

```cpp
Template
ForwardIterator1 find_first_of(ForwardIterator1 first1,
                               ForwardIterator1 last1,
                               ForwardIterator2 first2, 
                               ForwardIterator2 last2);

first1: Forward iterator to the first element 
       in the first range.
last1: Forward iterator to the last element 
       in the first range.
first2: Forward iterator to the first element
       in the second range.
last2: Forward iterator to the last element 
       in the second range.

Return Value: It returns an iterator to the 
              first element in [first1,last1) that is part of 
              [first2,last2). If no matches are found or [first2,
              last2) is empty, the function returns last1.

```

```cpp
// C++ program to demonstrate 
// the use of std::find_first_of
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;
int main()
{
    // Defining first container
    vector<int>v = {1, 3, 3, 3, 10, 1, 3, 3, 7, 7, 8} , i;

    // Defining second container
    vector<int>v1 = {1, 3, 10};

    vector<int>::iterator ip;

    // Using std::find_first_of
    ip = std::find_first_of(v.begin(), v.end(), v1.begin(),
                            v1.end());

    // Displaying the first common element found
    cout << *ip << "\n";

    // Finding the second common element
    ip = std::find_first_of(ip + 1, v.end(), v1.begin(),
                            v1.end());

    // Displaying the second common element found
    cout << *ip << "\n";

    return 0;
}
```

输出:

```cpp
1 
3

```

这里，在两个向量中，第一个公共元素是 1，为了找到第二个公共元素，我们将第一个范围的开头作为已经找到的第一个公共元素旁边的元素。

*   **By comparing using a pre-defined function:**

    语法:

    ```cpp
    Template
       ForwardIterator1 find_first_of (ForwardIterator1 first1, 
                                       ForwardIterator1 last1,
                                       ForwardIterator2 first2, 
                                       ForwardIterator2 last2,
                                       BinaryPredicate pred);

    Here, first1, last1, first2 and last2 are the same as
    previous case.

    Pred: Binary function that accepts two 
    elements as arguments (one of each of the two sequences, 
    in the same order), and returns a value convertible to 
    bool. The value returned indicates whether the elements 
    are considered to match in the context of this function.
    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Return Value: It returns an iterator to 
    the first element in [first1,last1) that is part of 
    [first2,last2). If no matches are found or [first2,last2) 
    is empty, the function returns last1.
    ```

    ```cpp
    // C++ program to demonstrate
    // the use of std::find_first_of
    #include<iostream>
    #include<vector>
    #include<algorithm>
    using namespace std;

    // Defining the BinaryFunction
    bool Pred (int a, int b)
    {
        if ( a % b == 0) {
            return 1;
        } else {
            return 0;
        }
    }
    int main()
    {
        // Defining first container
        vector<int>v = {1, 5, 7, 11, 13, 15, 30, 30, 7} , i;

        // Defining second container
        vector<int>v1 = {2, 3, 4};

        vector<int>::iterator ip;

        // Using std::find_first_of
        ip = std::find_first_of(v.begin(), v.end(), v1.begin(),
                                v1.end(), Pred);

        // Displaying the first element satisfying Pred()
        cout << *ip << "\n";

        return 0;
    }
    ```

    输出:

    ```cpp
    15

    ```

    这里，我们以这样一种方式操作二元函数，即我们试图在第一个容器中找到第一个数字，它是第二个容器中任何数字的倍数。在这个例子中，15 是第一个，因为它可以被 3 整除。

    **可能的应用:** std::find_first_of 可用于查找另一个容器中出现的任何元素的第一次出现。

    1.  One possible application of this is to find **the first vowel in a sentence.**

        ```cpp
        // C++ program to demonstrate the use of std::find_first_of
        #include<iostream>
        #include<vector>
        #include<string>
        #include<algorithm>
        using namespace std;
        int main()
        {
            // Defining first container
            string s1 = "You are reading about std::find_first_of";

            // Defining second container containing list of vowels
            string s2 = {'a', 'A', 'e', 'E', 'i', 'I', 'o', 'O', 
                        'u', 'U'};

            // Using std::find_first_of to find first occurrence of
            // a vowel
            auto ip = std::find_first_of(s1.begin(),s1.end(),
                                         s2.begin(), s2.end());

            // Displaying the first vowel found
            cout << "First vowel found at index "<< (ip - s1.begin()) 
                 << "\n";
            return 0;
        }
        ```

        输出:

        ```cpp
        First vowel found at index 1

        ```

        **解释:** std::find_first_of 在第一个容器中搜索第二个容器中任何元素的第一次出现，这样，句子中出现的第一个元音就被找到了。

    2.  It can also be used to find the **first odd and even numbers** present in list.

        ```cpp
        // C++ program to find the first occurrence of an odd
        // and even number
        #include<iostream>
        #include<vector>
        #include<algorithm>
        using namespace std;

        // Defining the Predicate Function to find first occurrence
        // of an odd number
        bool pred( int a, int b)
        {
            if (a % b != 0) {
                return 1;
            } else {
                return 0;
            }
        }

        // Defining the Predicate Function to find first occurrence
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

            // Using std::find_first_of to find the first 
            // occurrence of an odd number
            vector<int>::iterator ip;
            ip = std::find_first_of(v1.begin(), v1.end(), v2.begin(),
                               v2.end(), pred);

            // Displaying the index where the first odd number 
            // occurred
            cout << "First odd no. occurs at index " 
                 <<  (ip - v1.begin());

            // Using std::find_first_of to find the last occurrence   
            // of an even number
            ip = std::find_first_of(v1.begin(), v1.end(), v2.begin(),
                               v2.end(), pred1);

            // Displaying the index where the first even number 
            // occurred
            cout << "\nFirst even no. occurs at index " 
                 <<  (ip - v1.begin());

            return 0;
        }
        ```

        输出:

        ```cpp
        First odd no. occurs at index 0
        First even no. occurs at index 2

        ```

        **说明:**这里，我们已经将 2 存储在一个容器中，借助谓词函数，我们正在第一个容器中寻找不能被 2 整除(对于奇数)且能被 2 整除(对于偶数)的第一个数字。

**时间复杂度:** O(n1 * n2)，其中，n1 为第一范围的元素个数，n2 为第二范围的元素个数。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。