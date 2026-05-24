# 在 C++ STL 中列出 crbegin()和 crend()函数

> 原文:[https://www . geesforgeks . org/list-Cr begin-and-crend-function-in-c-STL/](https://www.geeksforgeeks.org/list-crbegin-and-crend-function-in-c-stl/)

1.  The **list::crbegin()** is a built-in function in c++ STL that returns a constant reverse iterator which points to the last element of the list i.e reversed beginning of container. The elements cannot be modified or changed as the iterator is a constant one.

    **语法:**

    ```cpp
    list_name.crbegin()
    ```

    **参数:**函数不接受任何参数。

    **返回值:**返回一个随机访问反向迭代器，指向列表的反向开头。

    下面的程序说明了上面的功能:

    ```cpp
    // C++ program to illustrate the
    // list::crbegin() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // declaration of the list
        list<int> lis = { 10, 20, 30, 40, 50 };

        // prints the last element
        cout << "The last element is: " << *lis.crbegin();
        cout << "\nList: ";

        for (auto it = lis.crbegin(); it != lis.crend(); ++ it)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    The last element is: 50
    List: 50 40 30 20 10

    ```

2.  The **list::crend()** is a built-in function in C++ STL that returns a constant reverse iterator which points to the theoretical element preceding the first element in the list i.e. the reverse end of the list. The elements cannot be modified or changed as the iterator is a constant one.

    **语法:**

    ```cpp
    list_name.crend()

    ```

    **参数:**函数不接受任何参数。

    **返回值:**返回一个常量随机反向迭代器，指向列表的反向端。

    下面的程序说明了上面的功能:

    ```cpp
    // C++ program to illustrate the
    // list::crend() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // declaration of the list
        list<int> lis = { 7, 6, 5, 4, 3, 2 };

        cout << "List: " << endl;

        for (auto it = lis.crbegin(); it != lis.crend(); ++ it)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    List: 
    2 3 4 5 6 7

    ```