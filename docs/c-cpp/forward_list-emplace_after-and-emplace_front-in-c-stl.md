# c++ STL 中的 forward_list 侵位 _after()和侵位 _front()

> 原文:[https://www . geesforgeks . org/forward _ list-posit _ after-and-posit _ front-in-c-STL/](https://www.geeksforgeeks.org/forward_list-emplace_after-and-emplace_front-in-c-stl/)

1.  The **forward_list::emplace_after()** is a builtin function in C++ STL which is used to insert a new element after the element at position specified in the argument. This insertion of the new element increases the size of the container by one.

    **语法:**

    ```cpp
    forward_list_name.emplace_after(iterator position, elements)
    ```

    **参数:**该函数接受两个强制参数，如下所述:

    *   **位置:**它指定迭代器，该迭代器指向容器中新元素将要插入的位置。
    *   **元素:**指定位置后要插入的新元素。

    **返回值:**这个函数返回一个迭代器，指向新插入的元素。

    下面的程序说明了上述功能:

    ```cpp
    // C++ program to illustrate the
    // forward_list::emplace_after() function
    #include <forward_list>
    #include <iostream>

    using namespace std;

    int main()
    {

        forward_list<int> fwlist = { 1, 2, 3, 4, 5 };

        auto it_new = fwlist.before_begin();

        // use of emplace_after function
        // inserts elements at positions
        it_new = fwlist.emplace_after(it_new, 8);
        it_new = fwlist.emplace_after(it_new, 10);

        // cout << "The elements are: "
        for (auto it = fwlist.cbegin(); it != fwlist.cend(); it++) {
            cout << *it << " ";
        }

        return 0;
    }
    ```

    **输出:**

    ```cpp
    The elements are: 8 10 1 2 3 4 5 
    ```

2.  The **forward_list::emplace_front()** is a built-in function in C++ which is used to insert a new element at the beginning of the forward_list just before the first element. This increases the size of container by one.

    **语法:**

    ```cpp
    forward_list_name.emplace_front(elements)
    ```

    **参数:**该函数接受一个强制参数*元素*，该元素将在容器的开始处插入。

    **返回值:**不返回任何内容。

    下面的程序说明了上面的功能。

    ```cpp
    // C++ program to illustrate the
    // forward_list::emplace_front() function
    #include <forward_list>
    #include <iostream>

    using namespace std;

    int main()
    {

        forward_list<int> fwlist = { 1, 2, 3, 4, 5 };

        // use of emplace_front function
        // inserts elements at front
        fwlist.emplace_front(8);
        fwlist.emplace_front(10);

        cout << "Elements are: ";
        // Auto iterator
        for (auto it = fwlist.cbegin(); it != fwlist.cend(); it++) {
            cout << *it << " ";
        }

        return 0;
    }
    ```

    **输出:**

    ```cpp
    Elements are: 10 8 1 2 3 4 5 
    ```