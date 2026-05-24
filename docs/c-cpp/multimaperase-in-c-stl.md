# c++ STL 中的 multimap::erase()

> 原文:[https://www.geeksforgeeks.org/multimaperase-in-c-stl/](https://www.geeksforgeeks.org/multimaperase-in-c-stl/)

**multimap::erase()**

2.  **Syntax for erasing a key:**

    ```cpp
    multimap_name.erase(key)

    ```

    **参数:**该功能接受一个强制参数*键*，指定要在多映射容器中擦除的键。

    **返回值:**函数不返回任何内容。它用指定的键擦除所有元素。

    ```cpp
    // C++ program to illustrate
    // multimap::erase(key)
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
        cout << "The multimap before using erase() is : \n";
        cout << "KEY\tELEMENT\n";
        for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
            cout << itr->first
                 << '\t' << itr->second << '\n';
        }

        // function to erase given keys
        mp.erase(1);
        mp.erase(2);

        // prints the elements
        cout << "\nThe multimap after applying erase() is : \n";
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
    The multimap before using erase() is : 
    KEY    ELEMENT
    1    40
    2    30
    2    20
    3    60
    5    50

    The multimap after applying erase() is : 
    KEY    ELEMENT
    5    50
    3    60

    ```