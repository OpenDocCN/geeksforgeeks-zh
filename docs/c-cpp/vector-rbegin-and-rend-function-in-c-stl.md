# c++ STL 中的向量 rbegin()和 rend()函数

> 原文:[https://www . geesforgeks . org/vector-rbe gin-and-rend-function-in-c-STL/](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/)

1.  **vector::rbegin()** is a built-in function in C++ STL which returns a reverse iterator pointing to the last element in the container.

    **语法:**

    ```cpp
    vector_name.rbegin()
    ```

    **参数:**函数不接受任何参数。

    **返回值:**函数返回一个反向迭代器，指向容器中的最后一个元素。

    演示 vector::rbegin()方法的程序:

    **程序 1:**

    ```cpp
    // CPP program to illustrate
    // the vector::rbegin() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        vector<int> v;
        v.push_back(11);
        v.push_back(12);
        v.push_back(13);
        v.push_back(14);
        v.push_back(15);

        // prints all the elements
        cout << "The vector elements in reverse order are:\n";
        for (auto it = v.rbegin(); it != v.rend(); it++)
            cout << *it << " ";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    The vector elements in reverse order are:
    15 14 13 12 11

    ```

2.  **vector::rend()** is a built-in function in C++ STL which returns a reverse iterator pointing to the theoretical element right before the first element in the array container.

    **语法:**

    ```cpp
    vector_name.rend()
    ```

    **参数:**函数不取任何参数。

    **返回值:**函数返回一个反向迭代器，指向数组容器中第一个元素之前的理论元素。

    演示 vector::rend()方法的程序:

    **程序 1:**

    ```cpp
    // CPP program to illustrate
    // the vector::rend() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        vector<int> v;
        v.push_back(11);
        v.push_back(12);
        v.push_back(13);
        v.push_back(14);
        v.push_back(15);

        cout << "The last element is: " << *v.rbegin();

        // prints all the elements
        cout << "\nThe vector elements in reverse order are:\n";
        for (auto it = v.rbegin(); it != v.rend(); it++)
            cout << *it << " ";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    The last element is: 15
    The vector elements in reverse order are:
    15 14 13 12 11

    ```