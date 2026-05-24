# c++ STL 中的列表合并()函数

> 原文:[https://www.geeksforgeeks.org/list-merge-function-in-c-stl/](https://www.geeksforgeeks.org/list-merge-function-in-c-stl/)

**列表::merge()** 是 C++ STL 中的一个内置函数，它将两个排序列表合并成一个。列表应该按升序排序。如果参数中没有传递比较器，那么它会将两个排序列表合并成一个排序列表。如果参数中传递了一个比较器，那么它会相应地合并列表，进行内部比较。

1.  **Syntax:**

    ```cpp
    list1_name.merge(list2_name)

    ```

    **参数:**该函数接受单个强制参数*列表 2_name* ，该参数指定要合并到列表 1 中的列表。

    **返回值:**函数不返回任何东西

    下面的程序演示了该功能:

    **程序 1:**

    ```cpp
    // program below demonstrates the
    // merge function in c++
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // declaring the lists
        // initially sorted
        list<int> list1 = { 10, 20, 30 };
        list<int> list2 = { 40, 50, 60 };

        // merge operation
        list2.merge(list1);

        cout << "List:  ";

        for (auto it = list2.begin(); it != list2.end(); ++ it)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    List:  10 20 30 40 50 60

    ```

2.  **Syntax:**

    ```cpp
    list1_name.merge(list2_name, comparator)

    ```

    **参数:**该函数接受两个参数，如下所述:

    *   **列表 2-名称–**指定列表 1 中要合并的列表 2。
    *   **比较器–**它是一个二进制谓词，接受与列表中包含的值类型相同的两个值，如果第一个参数被认为在它定义的严格弱排序中位于第二个参数之前，则返回 true，否则返回 false。

    **返回值:**函数不返回任何东西

    ```cpp
    // program below demonstrates the
    // merge function in c++
    #include <bits/stdc++.h>
    using namespace std;

    // comparator which compares elements internally
    bool comparator(int first, int second)
    {
        return first < second;
    }
    int main()
    {
        // declaring the lists
        list<int> list1 = { 1, 70, 80 };
        list<int> list2 = { 2, 3, 4 };

        // merge operation
        list1.merge(list2, comparator);

        cout << "List: ";

        for (auto it = list1.begin(); it != list1.end(); ++ it)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    List: 1 2 3 4 70 80

    ```