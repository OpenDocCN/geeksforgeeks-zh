# 在 C++ STL 中设置运算符=

> 原文:[https://www.geeksforgeeks.org/set-operator-in-c-stl/](https://www.geeksforgeeks.org/set-operator-in-c-stl/)

**'='** 是 **C++ STL** 中的一个运算符，它将一个**集合**复制(或移动)到另一个集合，并且集合::运算符=是对应的运算符函数。该功能有三个版本:

1.  The first version takes reference of an set as an argument and copies it to an set.

    **语法:**

    ```cpp
    ums1.operator=(set &set2)
    ```

    **参数:**第一个版本以集合的引用作为参数。

2.  The second version performs a move assignment i.e it moves the content of an set to another set.

    **语法:**

    ```cpp
    ums1.operator=(set &&set2)
    ```

    **参数:**第二个版本以集合的 r 值引用作为参数

3.  The third version assigns contents of an initializer list to an set.

    **语法:**

    ```cpp
    ums1.operator=(initializer list)
    ```

    **参数:**第三个版本以一个初始化列表作为参数。

    **返回值:**都返回这个指针的值(*this)。

    **以下程序说明了 set::operator= :**

    ```cpp
    // C++ code to illustrate the method
    // set::operator=()

    #include <iostream>
    #include <set>
    using namespace std;

    // merge function
    template <class T>
    T merge(T a, T b)
    {
        T t(a);
        t.insert(b.begin(), b.end());
        return t;
    }

    int main()
    {
        set<int> sample1, sample2, sample3;

        // List initialization
        sample1 = { 1, 2, 3, 4, 5 };
        sample2 = { 6, 7, 8, 1 };

        // Merge both sets and
        // move the result to sample3
        sample3 = merge(sample1, sample2);

        // copy assignment
        sample1 = sample3;

        // Print the sets
        for (auto it = sample1.begin(); it != sample1.end(); ++ it) {
            cout << *it << " ";
        }

        cout << endl;

        for (auto it = sample2.begin(); it != sample2.end(); ++ it) {
            cout << *it << " ";
        }

        cout << endl;

        for (auto it = sample3.begin(); it != sample3.end(); ++ it) {
            cout << *it << " ";
        }

        cout << endl;

        return 0;
    }
    ```

    **Output:**

    ```cpp
    1 2 3 4 5 6 7 8 
    1 6 7 8 
    1 2 3 4 5 6 7 8

    ```