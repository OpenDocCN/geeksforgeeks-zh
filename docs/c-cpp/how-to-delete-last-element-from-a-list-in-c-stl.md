# 如何在 C++ STL 中删除列表中的最后一个元素

> 原文:[https://www . geesforgeks . org/如何从 c-stl 列表中删除最后一个元素/](https://www.geeksforgeeks.org/how-to-delete-last-element-from-a-list-in-c-stl/)

给定一个[列表](https://www.geeksforgeeks.org/list-cpp-stl/)，任务是在 C++ 中从这个列表中移除最后一个元素。

**示例:**

```cpp
Input: list = [10 20 30 70 80 90 100 40 50 60]
Output: 10 20 30 40 50 60 70 80 90

Input: list = [1 2 3 4 5]
Output: 1 2 3 4

```

列表是一种关联容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦添加到列表中就不能修改，尽管可以删除和添加该元素的修改值。

通过传递迭代器，列表的最后一个元素可以被**删除。**

**语法:**

```cpp
iterator erase (const_iterator positionOfElementToBeDeleted);

```

**方法:**通过将其迭代器传递给擦除函数，可以轻松删除最后一个元素。要到达指向最后一个元素的迭代器，有两种方法:

1.  **Method 1:**

    ```cpp
    prev(listInt.end())
    ```

    下面是上述方法的实现:

    **程序 1:**

    ```cpp
    // C++ program to delete last element
    // of a List by passing its iterator

    #include <iostream>
    #include <list>
    using namespace std;

    // Function to print the list
    void printList(list<int> mylist)
    {

        // Get the iterator
        list<int>::iterator it;

        // printing all the elements of the list
        for (it = mylist.begin(); it != mylist.end(); ++ it)
            cout << ' ' << *it;
        cout << '\n';
    }

    // Function to delete last element of list
    // using method 1
    void deleteByMethod1(list<int> mylist)
    {

        // printing all the elements of the list
        cout << "\nList originally: ";
        printList(mylist);

        // Get the iterator
        list<int>::iterator it;

        // Get the positionOfElementToBeDeleted
        // using method 1
        it = prev(mylist.end());

        // Erase the last element
        // currently pointed by the iterator
        mylist.erase(it);

        // printing all the elements of the list
        cout << "List after deletion: ";
        printList(mylist);
    }

    // Driver code
    int main()
    {
        list<int> mylist;

        // Get the list
        for (int i = 1; i < 10; i++)
            mylist.push_back(i * 10);

        // Method 1 to get positionOfElementToBeDeleted
        deleteByMethod1(mylist);

        return 0;
    }
    ```

    **Output:**

    ```cpp
    List originally:  10 20 30 40 50 60 70 80 90
    List after deletion:  10 20 30 40 50 60 70 80

    ```

2.  **Method 2:**

    ```cpp
    list::iterator it = listInt.end(); 
    --it;

    ```

    下面是上述方法的实现:

    **程序 2:**

    ```cpp
    // C++ program to delete last element
    // of a List by passing its iterator

    #include <iostream>
    #include <list>
    using namespace std;

    // Function to print the list
    void printList(list<int> mylist)
    {

        // Get the iterator
        list<int>::iterator it;

        // printing all the elements of the list
        for (it = mylist.begin(); it != mylist.end(); ++ it)
            cout << ' ' << *it;
        cout << '\n';
    }

    // Function to delete last element of list
    // using method 2
    void deleteByMethod2(list<int> mylist)
    {

        // printing all the elements of the list
        cout << "\nList originally: ";
        printList(mylist);

        // Get the iterator
        list<int>::iterator it;

        // Get the positionOfElementToBeDeleted
        // using method 2
        it = --mylist.end();

        // Erase the last element
        // currently pointed by the iterator
        mylist.erase(it);

        // printing all the elements of the list
        cout << "List after deletion: ";
        printList(mylist);
    }

    // Driver code
    int main()
    {
        list<int> mylist;

        // Get the list
        for (int i = 1; i < 10; i++)
            mylist.push_back(i * 10);

        // Method 2 to get positionOfElementToBeDeleted
        deleteByMethod2(mylist);

        return 0;
    }
    ```

    **Output:**

    ```cpp
    List originally:  10 20 30 40 50 60 70 80 90
    List after deletion:  10 20 30 40 50 60 70 80

    ```