# boost::算法::equal()在 C++ 库中

> 原文:[https://www . geeksforgeeks . org/boostalgorithmequal-in-c-library/](https://www.geeksforgeeks.org/boostalgorithmequal-in-c-library/)

**[C++ boost 库](https://www.geeksforgeeks.org/advanced-c-boost-library/)** 中的 **equal()** 函数位于标题*下【boost/algorithm/cxx 11/equal . HPP】*测试两个序列是否包含相等的值。它返回一个布尔值，确定两个序列是否相同。

**语法**:

```cpp
bool equal ( InputIterator1 first1, InputIterator1 second1,
                  InputIterator2 first2, InputIterator2 second2 )
or 
bool equal ( InputIterator1 first1, InputIterator1 second1,
             InputIterator2 first2, InputIterator2 second2, 
             BinaryPredicate pred )

```

**参数**:该功能接受如下参数:

*   **first1** :指定第一序列中初始位置的输入迭代器。
*   **second1**: It specifies the input iterators to the final positions in the first sequence.
    *   **first2** :指定第二序列中初始位置的输入迭代器。
    *   **second2** :指定输入迭代器到第二序列的最后位置。
    *   **p:** 指定比较谓词(如果指定的话)。

    **返回值**:如果两个序列相同，函数返回真，否则返回假。

    **注**:以上功能针对 C++ 14 及以上运行。

    **程序-1** :

    ```cpp
    // C++ program to implement the
    // above mentioned function

    #include <bits/stdc++.h>
    #include <boost/algorithm/cxx14/equal.hpp>
    using namespace std;

    // Drivers code
    int main()
    {

        // Declares the sequences
        int a[] = { 1, 2, 5, 6, 8 };

        int b[] = { 1, 2, 5, 6, 8 };

        // Run the function
        bool ans
            = boost::algorithm::equal(a, a + 5, b, b + 5);

        // Condition to check
        if (ans == 1)
            cout << "Sequence1 and Sequence2 are equal";
        else
            cout << "Sequence1 and Sequence2 are not equal";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    Sequence1 and Sequence2 are equal

    ```

    **程序-2** :

    ```cpp
    // C++ program to implement the
    // above mentioned function

    #include <bits/stdc++.h>
    #include <boost/algorithm/cxx14/equal.hpp>
    using namespace std;

    // Drivers code
    int main()
    {

        // Declares the sequences
        int a[] = { 1, 2, 5, 6, 8 };

        int b[] = { 1, 2, 5 };

        // Run the function
        bool ans
            = boost::algorithm::equal(a, a + 5, b, b + 5);

        // Condition to check
        if (ans == 1)
            cout << "Sequence1 and Sequence2 are equal";
        else
            cout << "Sequence1 and Sequence2 are not equal";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    Sequence1 and Sequence2 are not equal

    ```

    **参考**:[https://www . boost . org/doc/libs/1 _ 70 _ 0/libs/algorithm/doc/html/algorithm/cxx 14 . html # the _ boost _ algorithm _ library。CXX14 .相等](https://www.boost.org/doc/libs/1_70_0/libs/algorithm/doc/html/algorithm/CXX14.html#the_boost_algorithm_library.CXX14.equal)