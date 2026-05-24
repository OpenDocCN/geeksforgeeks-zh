# 在 C++ STL 中映射 crbegin()和 crend()函数

> 原文:[https://www . geesforgeks . org/map-Cr begin-and-crend-function-in-c-STL/](https://www.geeksforgeeks.org/map-crbegin-and-crend-function-in-c-stl/)

1.  **map::crbegin()** is a built-in function in C++ STL which returns a constant reverse iterator referring to the last element in the map container. Since map container contains the element in an ordered way, crbegin() will point to that element that will come last according to the container’s sorting criterion.

    **语法:**

    ```cpp
    map_name.crbegin()

    ```

    **参数:**函数不接受任何参数。

    **返回值:**函数返回一个常量反向迭代器，引用映射容器中的最后一个元素。

    ```cpp
    // C++ program to illustrate
    // map::crbegin() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {

        // initialize container
        map<int, int> mp;

        // insert elements in random order
        mp.insert({ 2, 30 });
        mp.insert({ 1, 40 });
        mp.insert({ 3, 60 });
        mp.insert({ 4, 20 });
        mp.insert({ 5, 50 });

        auto ite = mp.crbegin();
        cout << "The last element is {" << ite->first
             << ", " << ite->second << "}\n";

        // prints the elements
        cout << "\nThe map in reverse order is: \n";
        cout << "KEY\tELEMENT\n";
        for (auto itr = mp.crbegin(); itr != mp.crend(); ++ itr) {
            cout << itr->first
                 << '\t' << itr->second << '\n';
        }
        return 0;
    }
    ```

    **Output:**

    ```cpp
    The last element is {5, 50}

    The map in reverse order is: 
    KEY    ELEMENT
    5    50
    4    20
    3    60
    2    30
    1    40

    ```