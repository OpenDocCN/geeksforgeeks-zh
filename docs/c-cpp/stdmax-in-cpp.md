# 标准::C++ 中的最大值

> 原文:[https://www.geeksforgeeks.org/stdmax-in-cpp/](https://www.geeksforgeeks.org/stdmax-in-cpp/)

**std::max** 在头文件<算法>中定义，用于找出传递给它的数字中最大的一个。如果有多个，它将返回其中的第一个。它可以以下列方式使用:

1.  它比较在其参数中传递的两个数字，并返回两者中较大的一个，如果两者相等，则返回第一个。
2.  它还可以使用**二进制函数**来比较两个数字，该函数由用户预定义，然后作为参数在 std::max()中传递。
3.  如果我们想在给定的列表中找到**最大的元素**，并且如果列表中存在多个元素，它会返回第一个元素，这也很有用。

**三个版本定义如下:**

1.  **使用“

    比较元素语法:

    ```cpp
    template <class t="">constexpr const T& max (const T& a, const T& b);</class>

    Here, a and b are the numbers to be compared.
    Returns: Larger of the two values.

    ```

    ## 卡片打印处理机(卡片打印处理器的缩写)

    ```cpp
    // C++ program to demonstrate the use of std::max
    // C++ program to demonstrate the use of std::max
    #include<iostream>
    #include<algorithm>
    using namespace std;
    int main()
    {
        // Comparing ASCII values of a and b
        cout << std::max('a','b') << "\n";

        // Returns the first one if both the numbers
        // are same
        cout << std::max(7,7);

    return 0;
    } 
    ```

    ## 蟒蛇 3

    ```cpp
    # Python 3 program to
    # demonstrate the use of std::max

    # Comparing ASCII
    # values of a and b
    print(max('a','b'))

    # Returns the first
    # one if both the numbers
    # are same
    print(max(7, 7))

    # This code is contributed by 
    # Smitha Dinesh Semwal
    ```

    输出:

    ```cpp
    b
    7

    ```** 
2.  ****使用预定义函数进行元素比较:**

    语法:

    ```cpp
    template <class t="" class="" compare="">constexpr const T& max (const T& a, const T& b, Compare comp);</class>

    Here, a and b are the numbers to be compared.

    comp: Binary function that accepts two values of type T as arguments, 
    and returns a value convertible to bool.
    The value returned indicates whether the element passed as first argument is considered less than the second.

    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Returns: Larger of the two values.

    ```

    ```cpp
    // C++ program to demonstrate the use of std::max
    #include<iostream>
    #include<algorithm>
    using namespace std;

    // Defining the binary function
    bool comp(int a, int b)
    {
        return (a < b);
    }
    int main()
    {
        int a = 7;
        int b = 28;

        cout << std::max(a,b,comp) << "\n";

        // Returns the first one if both the numbers
        // are same
        cout << std::max(7,7,comp);

    return 0;
    } 
    ```

    输出:

    ```cpp
    28
    7

    ```** 
***   **用于查找列表中的最大元素:**

    语法:

    ```cpp
    template <class t="" class="" compare="">constexpr T max (initializer_list <t>il, Compare comp);</t></class>

    Here, comp is optional and can be skipped.
    il: An initializer_list object.
    Returns: Largest of all the values.

    ```

    ```cpp
    // C++ program to demonstrate the use of std::max
    #include<iostream>
    #include<algorithm>
    using namespace std;

    // Defining the binary function
    bool comp(int a, int b)
    {
        return (a < b);
    }
    int main()
    {

        // Finding the largest of all the numbers
        cout << std::max({1, 2, 3, 4, 5, 10, -1, 7},comp) << "\n";

    return 0;
    } 
    ```

    输出:

    ```cpp
    10

    ```** 

**相关文章:**

*   [标准::max_element](https://www.geeksforgeeks.org/stdmax_element-in-cpp/)
*   [标准::分钟](https://www.geeksforgeeks.org/stdmin-in-cpp/)
*   [标准::相等](https://www.geeksforgeeks.org/stdequal-in-cpp/)
*   [标准::C++ 中的 min _ element](https://www.geeksforgeeks.org/stdmin_element-in-cpp/)

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。