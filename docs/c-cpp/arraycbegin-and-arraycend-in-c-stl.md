# c++ STL 中的数组::cbegin()和数组::cend()

> 原文:[https://www . geeksforgeeks . org/arrayccbegin-and-arraysnd-in-c-STL/](https://www.geeksforgeeks.org/arraycbegin-and-arraycend-in-c-stl/)

1.  **array::cbegin()** is a built-in function in C++ STL which returns a *const_iterator* pointing to the first element in the array. It cannot be used to modify the element in the array which is possible using array::begin().

    **语法:**

    ```cpp
    array_name.cbegin() 
    ```

    **参数:**函数不接受任何参数。

    **返回值:**函数返回一个指向数组中第一个元素的*常量 _ 迭代器*。

    **程序 1:**

    ```cpp
    // CPP program to illustrate
    // the array::cbegin() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        array<int, 5> arr = { 1, 5, 2, 4, 7 };

        // Prints the first element
        cout << "The first element is " << *(arr.cbegin()) << "\n";

        // Print all the elements
        cout << "The array elements are: ";
        for (auto it = arr.cbegin(); it != arr.cend(); it++)
            cout << *it << " ";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    The first element is 1
    The array elements are: 1 5 2 4 7

    ```

2.  **array::cend()** is a built-in function in C++ STL which returns a *const_iterator* pointing to the theoretical element after the last element in an array.

    **语法:**

    ```cpp
    array_name.cend() 
    ```

    **参数:**函数不接受任何参数。

    **返回值:**函数返回一个*常量 _ 迭代器*，指向数组中最后一个元素之后的理论元素。

    **程序 1:**

    ```cpp
    // CPP program to illustrate
    // the array::cend() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        array<int, 5> arr = { 1, 5, 2, 4, 7 };

        // prints all the elements
        cout << "The array elements are: ";
        for (auto it = arr.cbegin(); it != arr.cend(); it++)
            cout << *it << " ";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    The array elements are: 1 5 2 4 7

    ```