# c++ 中的 equal _ range

> 原文:[https://www.geeksforgeeks.org/equal_range-in-cpp/](https://www.geeksforgeeks.org/equal_range-in-cpp/)

**std::equal_range** 用于查找给定范围[第一个，最后一个]内的子范围，其所有元素都等于给定值。它**返回这样一个子范围的初始和最终界限。**

此函数要求根据某个条件对范围进行排序或分区，以便条件评估为 true 的所有元素都位于给定值的左侧，其余元素都位于其右侧。

它有两种使用方式，如下所示:

1.  **使用<比较元素:**

语法:

```cpp
Template
pair 
    equal_range (ForwardIterator first, ForwardIterator last, const T& val);

first: Forward iterator to the first element in the range.
last: Forward iterator to the last element in the range.
val: Value of the subrange to search for in the range.

Return Value: It returns a pair object, whose member pair::first 
is an iterator to the lower bound of the subrange of equivalent 
values, and pair::second its upper bound.
If there is no element equivalent to val, then both first and 
second points to the nearest element greater than val, or if val is
greater than any other value, then both of them point to last.

```

```cpp
// C++ program to demonstrate the use of std::equal_range
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 10, 10, 30, 30, 30, 100, 10,
                      300, 300, 70, 70, 80 };

    // Declaring an iterator to store the
    // return value of std::equal_range
    std::pair<std::vector<int>::iterator,
              std::vector<int>::iterator> ip;

    // Sorting the vector v
    sort(v.begin(), v.end());
    // v becomes 10 10 10 30 30 30 70 70 80 100 300 300

    // Using std::equal_range and comparing the elements
    // with 30
    ip = std::equal_range(v.begin(), v.begin() + 12, 30);

    // Displaying the subrange bounds
    cout << "30 is present in the sorted vector from index "
         << (ip.first - v.begin()) << " till "
         << (ip.second - v.begin());

    return 0;
}
```

输出:

```cpp
30 is present in the sorted vector from index 3 till 6

```

**说明:**在对向量 v1 进行排序之后，我们检查了存在 30 的界限，即从索引 3 到索引 6。

*   **By comparing using a pre-defined function:**

    语法:

    ```cpp
     pair 
        equal_range (ForwardIterator first, ForwardIterator last, 
                     const T& val, Compare comp);

    Here, first, last and val are the same as previous case.

    comp: Binary function that accepts two arguments of the type 
    pointed by ForwardIterator (and of type T), and returns a
    value convertible to bool. The value returned indicates 
    whether the first argument is considered to go before the
    second. 
    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Return Value: It returns a pair object, whose member 
    pair::first is an iterator to the lower bound of the subrange 
    of equivalent values, and pair::second its upper bound. 
    If there is no element equivalent to val, then both first and
    second point to the nearest element greater than val,
    or if val is greater than any other value, then both
    of them point to last.

    ```

    ```cpp
    // C++ program to demonstrate the use of std::equal_range
    #include <iostream>
    #include <algorithm>
    #include <string>
    #include <vector>
    #include <functional>
    using namespace std;

    // Defining the BinaryFunction
    bool comp(int a, int b)
    {
        return (a > b);
    }
    int main()
    {
        vector<int> v = { 10, 10, 30, 30, 30, 100, 10,
                          300, 300, 70, 70, 80 };

        // Declaring an iterator to store the
        // return value of std::equal_range
        std::pair<std::vector<int>::iterator,
                  std::vector<int>::iterator> ip;

        // Sorting the vector v in descending order
        sort(v.begin(), v.end(), greater<int>());
        // v becomes 300 300 100 80 70 70 30 30 30 10 10 10

        // Using std::equal_range and comparing the elements
        // with 10
        ip = std::equal_range(v.begin(), v.begin() + 12, 10, comp);

        // Displaying the subrange bounds
        cout << "10 is present in the sorted vector from index "
             << (ip.first - v.begin()) << " till "
             << (ip.second - v.begin());

        return 0;
    }
    ```

    输出:

    ```cpp
    10 is present in the sorted vector from index 9 till 12

    ```

    **哪里可以用？**

    1.  **[std::lower_bound](https://www.geeksforgeeks.org/stdlower_bound-in-c/) and [std::upper_bound](https://www.geeksforgeeks.org/stdupper_bound-in-cpp/) at one place:** This function can be used if we want to use both std::lower_bound and std::upper_bound at the same time, as its first pointer will be same as std::lower_bound and its second pointer will be same as std::upper_bound. So, there is no use of separately using them, if we have std::equal_range.

        ```cpp
        // C++ program to demonstrate the use of std::equal_range
        #include <iostream>
        #include <vector>
        #include <algorithm>
        using namespace std;
        int main()
        {
            vector<int> v = { 1, 2, 3, 4, 5, 5, 6, 7 };

            // Declaring an iterator to store the
            // return value of std::equal_range
            std::pair<std::vector<int>::iterator,
                      std::vector<int>::iterator> ip;

            // Using std::equal_range and comparing the elements
            // with 5
            ip = std::equal_range(v.begin(), v.end(), 5);

            // Displaying the subrange bounds
            cout << "std::lower_bound should be equal to "
                 << (ip.first - v.begin()) << " and std::upper_bound "
                 << "should be equal to " << (ip.second - v.begin());

            vector<int>::iterator i1, i2;

            // Using std::lower_bound
            i1 = std::lower_bound(v.begin(), v.end(), 5);
            cout << "\nstd::lower_bound is = " << (i1 - v.begin());

            // Using std::upper_bound
            i2 = std::upper_bound(v.begin(), v.end(), 5);
            cout << "\nstd::upper_bound is = " << (i2 - v.begin());

            return 0;
        }
        ```

        输出:

        ```cpp
        std::lower_bound should be equal to 4 and 
        std::upper_bound should be equal to 6
        std::lower_bound is = 4
        std::upper_bound is = 6

        ```

    本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。