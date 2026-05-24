# 删除 C++ STL 列表中的元素

> 原文:[https://www.geeksforgeeks.org/delete-elements-c-stl-list/](https://www.geeksforgeeks.org/delete-elements-c-stl-list/)

[如何在 C++ STL 列表中插入元素？](https://www.geeksforgeeks.org/insert-elements-c-stl-list/)

本文涵盖了 STL 列表中的删除方面。

1.  **Using list::erase()**: The purpose of this function is to remove the elements from list. Single or multiple contiguous elements in range can be removed using this function. This function takes 2 arguments, start iterator and end iterator.
    **Time complexity :** O(n) where (n is size of list).

    ```cpp
    // C++ code to demonstrate the working of erase()

    #include<iostream>
    #include<list> // for list operations
    using namespace std;

    int main()
    {
        // initializing list of integers
        list<int> list1={10,15,20,25,30,35};

        // declaring list iterators
        list<int>::iterator it = list1.begin();
        list<int>::iterator it1 = list1.begin();

        // incrementing the positions of iterators
        advance(it,2);
        advance(it1,5);

        // printing original list
        cout << "The original list is : ";
        for (list<int>::iterator i=list1.begin(); i!=list1.end(); i++)
           cout << *i << " ";

        cout << endl;

        // using erase() to erase single element
        // erases 20
        list1.erase(it);

        // list after deletion 1 element
        cout << "The list after deleting 1 element using erase() : ";
        for (list<int>::iterator i=list1.begin(); i!=list1.end(); i++)
           cout << *i << " ";

        cout << endl;

        it = list1.begin();

        // incrementing the positions of iterators
        advance(it,2);

        // using erase() to erase multiple elements
        // erases 25,30
        list1.erase(it,it1);

        // list after deletion of multiple elements
        cout << "The list after deleting multiple elements using erase() : ";
        for (list<int>::iterator i=list1.begin(); i!=list1.end(); i++)
           cout << *i << " ";

        cout << endl;

    }
    ```

    输出:

    ```cpp
    The original list is : 10 15 20 25 30 35 
    The list after deleting 1 element using erase() : 10 15 25 30 35 
    The list after deleting multiple elements using erase() : 10 15 35 

    ```

2.  **Using list::pop_front() and list::pop_back()**:
    *   **pop_back()** :此功能**从列表中删除最后一个元素**。这会将列表的大小减少 1。
        时间复杂度:O(1)
    *   **pop_front()** :此功能**从列表中移除第一个元素**，并移动后续元素。这会将列表的大小减少 1。
        时间复杂度:O(1)

    ```cpp
    // C++ code to demonstrate the working of pop_front()
    // and pop_back()

    #include<iostream>
    #include<list> // for list operations
    using namespace std;

    int main()
    {
        // initializing list of integers
        list<int> list1={10,15,20,25,30,35};

        // printing original list
        cout << "The original list is : ";
        for (list<int>::iterator i=list1.begin(); i!=list1.end(); i++)
           cout << *i << " ";

        cout << endl;

        // using pop_front() to erase first element of list
        // pops 10
        list1.pop_front();

        // list after deleting first element
        cout << "The list after deleting first element using pop_front() : ";
        for (list<int>::iterator i=list1.begin(); i!=list1.end(); i++)
           cout << *i << " ";

        cout << endl;

        // using pop_back() to erase last element of list
        // pops 35
        list1.pop_back();

        // list after deleting last element
        cout << "The list after deleting last element using pop_back() : ";
        for (list<int>::iterator i=list1.begin(); i!=list1.end(); i++)
           cout << *i << " ";

        cout << endl;

    }
    ```

    输出:

    ```cpp
    The original list is : 10 15 20 25 30 35 
    The list after deleting first element using pop_front() : 15 20 25 30 35 
    The list after deleting last element using pop_back() : 15 20 25 30 

    ```

3.  **Using remove() and remove_if()**:
    *   **remove()** :此函数**删除在其参数中传递的值**的所有出现。与“erase()”不同的是，“erase()”按位置删除值，其中“remove()”删除传递的值。列表的大小会因删除的事件数量而减小。
        时间复杂度: **O(n)**
    *   **remove_if()** :该函数**删除**出现的**值，该值返回“真”给在其参数中传递的函数**。
        时间复杂度: **O(n)**

    ```cpp
    // C++ code to demonstrate the working of remove()
    // remove_if()

    #include<iostream>
    #include<list> // for list operations
    using namespace std;

    // function to pass in argument of "remove_if()"
    bool is_div_5(const int& num) { return num%5==0;} 

    int main()
    {
        // initializing list of integers
        list<int> list1={10,14,20,22,30,33,22};

        // printing original list
        cout << "The original list is : ";
        for (list<int>::iterator i=list1.begin(); i!=list1.end(); i++)
           cout << *i << " ";

        cout << endl;

        // using remove() to delete all occurrences of 22
        list1.remove(22);

        // list after deleting all 22 occurrences
        cout << "The list after deleting all 22 occurrences : ";
        for (list<int>::iterator i=list1.begin(); i!=list1.end(); i++)
           cout << *i << " ";

        cout << endl;

        // using remove_if() to delete multiple of 5 
        list1.remove_if(is_div_5);

        // list after deleting all multiples of 5
        cout << "The list after deleting all multiples of 5 : ";
        for (list<int>::iterator i=list1.begin(); i!=list1.end(); i++)
           cout << *i << " ";

        cout << endl;

    }
    ```

    输出:

    ```cpp
    The original list is : 10 14 20 22 30 33 22 
    The list after deleting all 22 occurrences : 10 14 20 30 33 
    The list after deleting all multiples of 5 : 14 33 

    ```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。