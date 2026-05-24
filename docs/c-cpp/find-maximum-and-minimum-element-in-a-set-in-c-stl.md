# 在 C++ STL 中查找集合中的最大和最小元素

> 原文:[https://www . geesforgeks . org/find-c-STL 中的最大和最小元素集/](https://www.geeksforgeeks.org/find-maximum-and-minimum-element-in-a-set-in-c-stl/)

给定一个集合，任务是在 C++ STL 中找到这个集合的最大和最小元素。

**示例:**

```cpp
Input: set={1, 6, 15, 10, 5}
Output: max = 15, min = 1

Input: set={10, 20, 30, 40, 50, 60}
Output: max = 60, min = 10

```

*   **Using [set.begin() and set.end() methods](https://www.geeksforgeeks.org/setbegin-setend-c-stl/)**

    **方法:**集合中的元素按排序顺序存储。因此，集合中的最小元素位于第一个元素中，最大元素位于最后一个元素中。因此，可以分别借助 set.begin()和 set.end()方法来获取第一个和最后一个元素。

    **程序:**

    ```cpp
    #include <bits/stdc++.h>
    using namespace std;

    // Function to print the set
    void printSet(set<int> my_set)
    {

        // Print the set
        cout << "Set: ";
        for (auto i : my_set)
            cout << i << " ";

        cout << '\n';
    }

    // Function to find the maximum element
    int findMax(set<int> my_set)
    {

        // Get the maximum element
        int max_element;
        if (!my_set.empty())
            max_element = *(my_set.rbegin());

        // return the maximum element
        return max_element;
    }

    // Function to find the minimum element
    int findMin(set<int> my_set)
    {

        // Get the minimum element
        int min_element;
        if (!my_set.empty())
            min_element = *my_set.begin();

        // return the minimum element
        return min_element;
    }

    int main()
    {

        // Get the set
        set<int> my_set;

        // Add the elements in the set
        my_set.insert(1);
        my_set.insert(6);
        my_set.insert(15);
        my_set.insert(10);
        my_set.insert(5);

        // Print the set
        printSet(my_set);

        // Get the minimum element
        cout << "Minimum element: "
             << findMin(my_set)
             << endl;

        // Get the maximum element
        cout << "Maximum element: "
             << findMax(my_set)
             << endl;
    }
    ```

    **Output:**

    ```cpp
    Set: 1 5 6 10 15 
    Minimum element: 1
    Maximum element: 15

    ```

*   **Using [set.rbegin() and set.rend() methods](https://www.geeksforgeeks.org/setrbegin-and-setrend-in-c-stl/)**

    **方法:**集合中的元素按排序顺序存储。因此，集合中的最小元素位于第一个元素中，最大元素位于最后一个元素中。因此，可以分别借助 set.rend()和 set.rbegin()方法来获取第一个和最后一个元素。

    **程序:**

    ```cpp
    #include <bits/stdc++.h>
    using namespace std;

    // Function to print the set
    void printSet(set<int> my_set)
    {

        // Print the set
        cout << "Set: ";
        for (auto i : my_set)
            cout << i << " ";

        cout << '\n';
    }

    // Function to find the maximum element
    int findMax(set<int> my_set)
    {

        // Get the maximum element
        int max_element;
        if (!my_set.empty())
            max_element = *my_set.rbegin();

        // return the maximum element
        return max_element;
    }

    // Function to find the minimum element
    int findMin(set<int> my_set)
    {

        // Get the minimum element
        int min_element;
        if (!my_set.empty())
            min_element = *(--my_set.rend());

        // return the minimum element
        return min_element;
    }

    int main()
    {

        // Get the set
        set<int> my_set;

        // Add the elements in the set
        my_set.insert(1);
        my_set.insert(6);
        my_set.insert(15);
        my_set.insert(10);
        my_set.insert(5);

        // Print the set
        printSet(my_set);

        // Get the minimum element
        cout << "Minimum element: "
             << findMin(my_set)
             << endl;

        // Get the maximum element
        cout << "Maximum element: "
             << findMax(my_set)
             << endl;
    }
    ```

    **Output:**

    ```cpp
    Set: 1 5 6 10 15 
    Minimum element: 1
    Maximum element: 15

    ```