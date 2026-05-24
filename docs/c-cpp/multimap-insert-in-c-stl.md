# c++ STL 中的多映射插入()

> 原文:[https://www.geeksforgeeks.org/multimap-insert-in-c-stl/](https://www.geeksforgeeks.org/multimap-insert-in-c-stl/)

**multimap::insert** 是 C++ STL 中的内置函数，用于在 multimap 容器中插入元素。

1.  **Syntax:**

    ```cpp
    iterator multimap_name.insert({key, element})

    ```

    **参数:**该函数接受一个由要插入到多映射容器中的键和元素组成的对。

    **返回值:**函数返回一个迭代器，指向容器中的新元素。

    ```cpp
    // C++ program to illustrate
    // multimap::insert({key, element})
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
        mp.insert({ 2, 20 });
        mp.insert({ 5, 50 });

        // prints the elements
        cout << "KEY\tELEMENT\n";
        for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
            cout << itr->first
                 << '\t' << itr->second << '\n';
        }
        return 0;
    }
    ```

    **Output:**

    ```cpp
    KEY    ELEMENT
    1    40
    2    30
    2    20
    3    60
    5    50

    ```