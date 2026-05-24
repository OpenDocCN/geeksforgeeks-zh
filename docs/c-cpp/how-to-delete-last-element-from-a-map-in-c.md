# 如何在 C++ 中删除地图的最后一个元素

> 原文:[https://www . geesforgeks . org/如何从 c-in-map 中删除最后一个元素/](https://www.geeksforgeeks.org/how-to-delete-last-element-from-a-map-in-c/)

如果我们希望从[地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)中删除最后一个元素，我们可以使用以下方法:

1.  **使用 prev(MP . end())**:prev 函数的作用是，从给定的迭代器向后退一步。因此使用 **prev** 函数和 **mp.end()** 将返回一个指向地图最后一个元素的迭代器。
    实现:

    ```cpp
    #include <bits/stdc++.h>

    using namespace std;

    int main()
    {

        map<int, int> mp;

        // Adding some elements in mp
        mp[1] = 10;
        mp[2] = 20;
        mp[3] = 30;

        cout << "Contents of mp before deleting"
               " the last element :\n";
        for (auto it = mp.begin(); it != mp.end(); it++)
            cout << it->first << " ==> "
                 << it->second << "\n";

        cout << "Deleting the last element from"
               " the map.\n";
        mp.erase(prev(mp.end()));

        cout << "Contents of mp after deleting the last"
                " element :\n";
        for (auto it = mp.begin(); it != mp.end(); it++)
            cout << it->first << " ==> "
                 << it->second << "\n";
    }
    ```

    **输出:**

    ```cpp
    Contents of mp before deleting the last element :
    1 ==> 10
    2 ==> 20
    3 ==> 30
    Deleting the last element from the map.
    Contents of mp after deleting the last element :
    1 ==> 10
    2 ==> 20

    ```

2.  **使用迭代器–**:将一个迭代器设置为 mp.end()，然后使用迭代器–到达映射中的最后一个元素，然后使用 erase 函数将其删除。
    实现:

    ```cpp
    #include <bits/stdc++.h>

    using namespace std;

    int main()
    {

        map<int, int> mp;
        // Adding some elements in mp
        mp[1] = 10;
        mp[2] = 20;
        mp[3] = 30;

        cout << "Contents of mp before deleting "
                "the last element :\n";
        for (auto it = mp.begin(); it != mp.end(); it++)
            cout << it->first << " ==> " 
                 << it->second << "\n";

        cout << "Deleting the last element from"
                " the map.\n";
        auto it = mp.end();
        it--;
        mp.erase(it);

        cout << "Contents of mp after deleting the"
                " last element :\n";
        for (auto it = mp.begin(); it != mp.end(); it++)
            cout << it->first << " ==> "
                 << it->second << "\n";
    }
    ```

    **输出:**

    ```cpp
    Contents of mp before deleting the last element :
    1 ==> 10
    2 ==> 20
    3 ==> 30
    Deleting the last element from the map.
    Contents of mp after deleting the last element :
    1 ==> 10
    2 ==> 20

    ```