# 在 C++ STL 中列出 rbegin()和 rend()函数

> 原文:[https://www . geesforgeks . org/list-rbe gin-and-rend-function-in-c-STL/](https://www.geeksforgeeks.org/list-rbegin-and-rend-function-in-c-stl/)

1.  **list::rbegin()** is an inbuilt function in C++ STL that returns a reverse iterator which points to the last element of the list.

    **语法:**

    ```cpp
    list_name.rbegin()
    ```

    **参数:**此功能不接受任何参数。

    **返回值:**返回一个反向迭代器，指向列表的最后一个元素。

    下面的程序说明了上面的功能:

    ```cpp
    // C++ program to illustrate the
    // list::rbegin() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        list<int> lis = { 10, 20, 30, 40, 50 };

        cout << "The list in reverse order: ";

        for (auto it = lis.rbegin(); it != lis.rend(); ++ it)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    The list in reverse order: 50 40 30 20 10

    ```

2.  **list::rend()** is an inbuilt function in C++ STL that returns a reverse iterator which points to the position before the beginning of the list.

    **语法:**

    ```cpp
    list_name.rend()
    ```

    **参数:**函数不接受任何参数。

    **返回值:**返回一个反向迭代器，指向列表开始前的位置。

    下面的程序说明了上面的功能:

    ```cpp
    // C++ program to illustrate the
    // list::rbegin() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        list<int> lis = { 10, 20, 30, 40, 50 };

        cout << "The list in reverse order: ";

        for (auto it = lis.rbegin(); it != lis.rend(); ++ it)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    The list in reverse order: 50 40 30 20 10

    ```