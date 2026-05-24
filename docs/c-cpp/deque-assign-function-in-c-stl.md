# c++ STL 中的 deque assign()函数

> 原文:[https://www . geesforgeks . org/deque-assign-function-in-c-STL/](https://www.geeksforgeeks.org/deque-assign-function-in-c-stl/)

**deque::assign()** 是 C++ STL 中的内置函数，用于为相同或不同的 deque 容器赋值。在同一个程序中被多次调用时，该函数会破坏先前元素的值，并向容器重新分配一组新的元素。

1.  **Syntax:**

    ```cpp
    deque_name.assign(size, val)
    ```

    **参数:**该函数接受两个参数，如下所述:

    *   **大小:**它指定要分配给容器的值的数量。
    *   **val:** 它指定要分配给容器的值。

    **返回值:**函数不返回任何内容。

    以下程序说明了上述功能:

    **程序 1:**

    ```cpp
    // CPP program to demonstrate the
    // deque::assign() function
    #include <bits/stdc++.h>
    using namespace std;
    int main()
    {
        deque<int> dq;

        // assign 5 values of 10 each
        dq.assign(5, 10);

        cout << "The deque elements: ";
        for (auto it = dq.begin(); it != dq.end(); it++)
            cout << *it << " ";

        // re-assigns 10 values of 15 each
        dq.assign(10, 15);

        cout << "\nThe deque elements: ";
        for (auto it = dq.begin(); it != dq.end(); it++)
            cout << *it << " ";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    The deque elements: 10 10 10 10 10 
    The deque elements: 15 15 15 15 15 15 15 15 15 15

    ```

2.  **Syntax:**

    ```cpp
    deque1_name.assign(iterator1, iterator2)
    ```

    **参数:**该函数接受两个参数，如下所述:

    *   **迭代器 1:** 它指定迭代器，该迭代器指向容器(dequee，array，…)的起始元素，该容器的元素将被转移到 dequee 1。
    *   **迭代器 2:** 它指定指向容器(dequee，array，…)的最后一个元素的迭代器，该容器的元素将被转移到 dequee 1

    **返回值:**函数不返回任何内容。

    以下程序说明了上述功能:

    **程序 1:**

    ```cpp
    // CPP program to demonstrate the
    // deque::assign() function
    #include <bits/stdc++.h>
    using namespace std;
    int main()
    {
        deque<int> dq;

        // assign 5 values of 10 each
        dq.assign(5, 10);

        cout << "The deque elements: ";
        for (auto it = dq.begin(); it != dq.end(); it++)
            cout << *it << " ";

        deque<int> dq1;

        // assigns all elements from
        // the second position to deque1
        dq1.assign(dq.begin() + 1, dq.end());

        cout << "\nThe deque1 elements: ";
        for (auto it = dq1.begin(); it != dq1.end(); it++)
            cout << *it << " ";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    The deque elements: 10 10 10 10 10 
    The deque1 elements: 10 10 10 10

    ```