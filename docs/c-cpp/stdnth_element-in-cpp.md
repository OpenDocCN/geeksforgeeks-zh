# std::nth_element in C++

> 原文:[https://www.geeksforgeeks.org/stdnth_element-in-cpp/](https://www.geeksforgeeks.org/stdnth_element-in-cpp/)

**std::nth_element()** 是一种 STL 算法，它以这样一种方式重新排列列表，即如果我们对列表进行排序，第 n 个位置的元素就是应该在该位置的元素。

它不会对列表进行排序，只是第 n 个元素之前的所有元素都不会大于它，之后的所有元素都不会小于它。
**有两个版本，定义如下:**

1.  **Comparing elements using "
    syntax:

    ```cpp
    template 
    void nth_element (RandomAccessIterator first, RandomAccessIterator nth,
                      RandomAccessIterator last);

    first: Random-access iterator to the first element in the list.
    last: Random-access iterator to the last element in the list.
    nth: Random-access iterator pointing to the position in the list, 
    which should be sorted.
    If it points to end, then this function will do nothing.

    Return Value: Since, return type is void, so it doesnot return any value.

    ```

    ```cpp
    // C++ program to demonstrate the use of std::nth_element
    #include <iostream>
    #include <algorithm>
    using namespace std;
    int main()
    {
        int v[] = { 3, 2, 10, 45, 33, 56, 23, 47 }, i;

        // Using std::nth_element with n as 5
        std::nth_element(v, v + 4, v + 8);

        // Since, n is 5 so 5th element should be sorted
        for (i = 0; i < 8; ++ i) {
            cout << v[i] << " ";
        }
        return 0;
    }
    ```

    Output:

    ```cpp
    3 2 10 23 33 56 45 47 

    ```

    Here, the fifth element is 33, all elements on its left are smaller than it, and all elements on its right are larger than it.** 
2.  ****By comparing using a pre-defined function:**

    Syntax:

    ```cpp
    template 
    void nth_element (RandomAccessIterator first, RandomAccessIterator nth,
                      RandomAccessIterator last, Compare comp); 
    Here, first, last and nth arguments are the same as previous case.

    comp: Binary function that accepts two elements in the range 
    as arguments, and returns a value convertible to bool.
    The value returned indicates whether the element passed as first argument is 
    considered to go before the second in the specific strict weak ordering it defines.
    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Return Value: Since, its return type is void, so it doesnot return any value.

    ```

    ```cpp
    // C++ program to demonstrate the use of std::nth_element
    #include <iostream>
    #include <algorithm>
    using namespace std;

    // Defining the BinaryFunction
    bool comp(int a, int b)
    {
        return (a < b);
    }
    int main()
    {
        int v[] = { 3, 2, 10, 45, 33, 56, 23, 47 }, i;

        // Using std::nth_element with n as 6
        std::nth_element(v, v + 5, v + 8, comp);

        // Since, n is 6 so 6th element should be the same
        // as the sixth element present if we sort this array
        // Sorted Array
        /* 2 3 10 23 33 45 47 56 */
        for (i = 0; i < 8; ++ i) {
            cout << v[i] << " ";
        }
        return 0;
    }
    ```

    Output:

    ```cpp
    33 2 10 23 3 45 47 56 

    ```

    In this code, Since the nth element pointed by the second parameter in std::nth_element is the sixth element of array V, this means that after applying std::nth_element, the sixth element in the array should be the element that will appear if the whole array is sorted, that is, 45\.

    All elements on its left are either less than it or equal to it, and elements on its right are greater than it.

    **The purpose of binary function comp:** STD:: nth _ element partially sorts the range [first and last] in ascending order, so that any I in the range [first and nth] and any J in the range [nth and last] meet the conditions. * I [ Therefore, comp () is used to ensure that all elements before the nth element are less than those after the nth element.** 
**": < >**

**哪里可以应用 std::nth_element()？**

1.  It can be used if we want to find the **first n smallest numbers**, but they may or maynot be ordered.

    ```cpp
    // C++ program to find first n smallest numbers
    #include <iostream>
    #include <algorithm>
    using namespace std;
    int main()
    {
        int v[] = { 30, 20, 10, 40, 60, 50, 70, 80 }, i;

        // Using std::nth_element with n as 3
        std::nth_element(v, v + 2, v + 8);

        // Since, n is 3 so now first three numbers will be the
        // three smallest numbers in the whole array
        // Displaying first three smallest number
        for (i = 0; i < 3; ++ i) 
        {
            cout << v[i] << " ";
        }
        return 0;
    }
    ```

    输出:

    ```cpp
    20 10 30

    ```

2.  Just like first n smallest number, we can also find **first n largest numbers**, by just changing the Binary Function passed as argument in std::nth_element.

    ```cpp
    // C++ program to find first n largest numbers
    #include <iostream>
    #include <algorithm>
    using namespace std;
    int main()
    {
        int v[] = { 30, 20, 50, 60, 70, 10, 80, 40 }, i;

        // Using std::nth_element with n as 2
        std::nth_element(v, v + 1, v + 8, std::greater<int>());

        // Since, n is 2 so first 2 elements will be the largest
        // among all the array elements
        // Displaying First 2 elements
        for (i = 0; i < 2; ++ i) 
        {
            cout << v[i] << " ";
        }
        return 0;
    }
    ```

    输出:

    ```cpp
    80 70

    ```

    在这里，我们传递了更大的<int>()作为二进制函数，所以现在第 n 个元素将是应该在第 n 个位置的元素，如果我们按降序对给定的数组进行排序，那么前 n 个元素将是前 n 个最大的元素。</int>

3.  可以用来求给定元素的**中值。**

    ```cpp
    // C++ program to find the median of the vector
    #include <iostream>
    #include <algorithm>
    #include <vector>
    using namespace std;
    int main()
    {
        vector<int> v = { 3, 2, 10, 45, 33, 56, 23, 47, 60 }, i;

        // Using std::nth_element with n as v.size()/2 + 1
        std::nth_element(v.begin(), v.begin() + v.size() / 2, v.end());

        cout << "The median of the array is " << v[v.size() / 2];

        return 0;
    }
    ```

    输出:

    ```cpp
    The median of the array is 33

    ```

这里排序后的数组将是 2 3 10 23 3 3 45 47 56 60，因此有 9 个元素，中间值将是中间元素，即第 5 个元素:33。

**STD::n th _ element()的时间复杂度:** O(n)，n 为第一个和最后一个之间的距离。
**相关文章:**

*   [标准::搜索](https://www.geeksforgeeks.org/stdsearch-in-c/)
*   [标准::查找](https://www.geeksforgeeks.org/stdfind-in-c/)
*   [std::find_if，std::find_if_not](https://www.geeksforgeeks.org/stdfind_if-stdfind_if_not-in-c/)
*   [std::find_end](https://www.geeksforgeeks.org/stdfind_end-in-cpp/)
*   [标准::排序](https://www.geeksforgeeks.org/sort-c-stl/)

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。