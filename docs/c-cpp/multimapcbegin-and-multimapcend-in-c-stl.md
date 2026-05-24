# c++ STL 中的 multimap::cbegin()和 multimap::cend()

> 原文:[https://www . geesforgeks . org/multimapcbegin-and-multimapcend-in-c-STL/](https://www.geeksforgeeks.org/multimapcbegin-and-multimapcend-in-c-stl/)

1.  **multimap::cbegin()** is a built-in function in C++ STL which returns a constant iterator referring to the first element in the multimap container. Since multimap container contains the element in an ordered way, cbegin() will point to that element that will come first according to the container’s sorting criterion.

    **语法:**

    ```cpp
    multimap_name.cbegin()

    ```

    **参数:**函数不接受任何参数。

    **返回值:**函数返回一个常量迭代器，引用 multimap 容器中的第一个元素。

    ```cpp
    // C++ program to illustrate
    // the multimap::cbegin() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {

        // initialize container
        multimap<int, int> mp;

        // insert elements in random order
        mp.insert({ 2, 30 });
        mp.insert({ 1, 40 });
        mp.insert({ 3, 60 });
        mp.insert({ 4, 20 });
        mp.insert({ 5, 50 });

        auto ite = mp.cbegin();

        cout << "The first element is: ";
        cout << "{" << ite->first << ", "
             << ite->second << "}\n";

        // prints the elements
        cout << "\nThe multimap is : \n";
        cout << "KEY\tELEMENT\n";
        for (auto itr = mp.cbegin(); itr != mp.cend(); ++ itr) {
            cout << itr->first
                 << '\t' << itr->second << '\n';
        }
        return 0;
    }
    ```

    **Output:**

    ```cpp
    The first element is: {1, 40}

    The multimap is : 
    KEY    ELEMENT
    1    40
    2    30
    3    60
    4    20
    5    50

    ```