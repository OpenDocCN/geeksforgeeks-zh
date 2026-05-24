# c++ STL 中的多集 rbegin()和 rend()函数

> 原文:[https://www . geesforgeks . org/multist-rbegin-and-rend-function-in-c-STL/](https://www.geeksforgeeks.org/multiset-rbegin-and-rend-function-in-c-stl/)

1.  **multiset::rbegin()** is a built-in function in C++ STL which returns a reverse iterator pointing to the last element in the multiset container.

    **语法:**

    ```cpp
    reverse_iterator multiset_name.rbegin()

    ```

    **参数:**函数不取任何参数。

    **返回值:**函数返回一个反向迭代器，指向容器中的最后一个元素。

    下面的程序说明了 multist::rbe gin()方法:

    ```cpp
    // CPP program to demonstrate the
    // multiset::rbegin() function
    #include <bits/stdc++.h>
    using namespace std;
    int main()
    {

        int arr[] = { 15, 12, 15, 11, 10, 10 };

        // initializes the set from an array
        multiset<int> s(arr, arr + 6);

        multiset<int>::reverse_iterator rit;

        // prints all elements in reverse order
        for (rit = s.rbegin(); rit != s.rend(); rit++)
            cout << *rit << " ";

        cout << "\nThe last element in multiset is " << *(s.rbegin());

        return 0;
    }
    ```

    **Output:**

    ```cpp
    15 15 12 11 10 10 
    The last element in multiset is 15

    ```

2.  **multiset::rend()** in an inbuilt function in C++ STL which returns a reverse iterator pointing to the theoretical element right before the first element in the multiset container.

    **语法:**

    ```cpp
    reverse_iterator multiset_name.rend()

    ```

    **参数:**函数不接受任何参数。

    **返回值:**函数返回一个反向迭代器，指向多集容器中第一个元素之前的理论元素。

    下面的程序说明了 multist::rend()函数:

    ```cpp
    // CPP program to demonstrate the
    // multiset::rend() function
    #include <bits/stdc++.h>
    using namespace std;
    int main()
    {

        int arr[] = { 15, 13, 15, 11, 13, 10 };

        // initializes the set from an array
        multiset<int> s(arr, arr + 6);

        multiset<int>::reverse_iterator rit;

        // prints all elements in reverse order
        for (rit = s.rbegin(); rit != s.rend(); rit++)
            cout << *rit << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    15 15 13 13 11 10

    ```