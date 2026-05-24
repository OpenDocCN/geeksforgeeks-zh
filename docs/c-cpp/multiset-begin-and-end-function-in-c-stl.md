# c++ STL 中的多集 begin()和 end()函数

> 原文:[https://www . geesforgeks . org/multist-begin-and-end-function-in-c-STL/](https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/)

1.  The **multiset::begin()** is a built-in function in C++ STL which returns an iterator pointing to the first element in the multiset container. Since multiset always contains elements in an ordered way, begin() always points to the first element according to the sorting criterion.

    **语法:**

    ```cpp
    iterator multiset_name.begin()

    ```

    **参数:**函数不接受任何参数。

    **返回值:**函数返回指向容器中第一个元素的迭代器。

    下面的程序说明了上述功能:

    ```cpp
    // CPP program to demonstrate the
    // multiset::begin() function
    #include <bits/stdc++.h>
    using namespace std;
    int main()
    {

        int arr[] = { 14, 10, 15, 11, 10 };

        // initializes the set from an array
        multiset<int> s(arr, arr + 5);

        // Print the first element
        cout << "The first element is: " << *(s.begin()) << endl;

        // prints all elements in set
        for (auto it = s.begin(); it != s.end(); it++)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    The first element is: 10
    10 10 11 14 15

    ```

2.  The **multiset::end()** is a built-in function in C++ STL which returns an iterator pointing to the position past the last element in the container.
    **Syntax:**

    ```cpp
    iterator multiset_name.end()

    ```

    **参数:**函数不接受任何参数。

    **返回值:**函数返回一个迭代器，指向多集容器中容器中最后一个元素的位置。

    下面的程序说明了上述功能:

    ```cpp
    // CPP program to demonstrate the
    // multiset::end() function
    #include <bits/stdc++.h>
    using namespace std;
    int main()
    {

        int arr[] = { 14, 10, 15, 11, 10, 12, 17, 12 };

        // initializes the set from an array
        multiset<int> s(arr, arr + 8);

        // prints all elements in set
        for (auto it = s.begin(); it != s.end(); it++)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    10 10 11 12 12 14 15 17

    ```