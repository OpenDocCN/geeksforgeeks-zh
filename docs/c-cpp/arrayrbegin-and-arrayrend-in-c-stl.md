# c++ STL 中的数组::rbegin()和数组::rend()

> 原文:[https://www . geeksforgeeks . org/arrayr begin-and-arrayrend-in-c-STL/](https://www.geeksforgeeks.org/arrayrbegin-and-arrayrend-in-c-stl/)

1.  **array::rbegin()** is a built-in function in C++ STL which returns a reverse iterator pointing to the last element in the container.

    **语法:**

    ```cpp
    array_name.rbegin()
    ```

    **参数:**函数不接受任何参数。

    **返回值:**函数返回一个反向迭代器，指向容器中的最后一个元素。

    演示数组::rbegin()方法的程序:

    **程序 1:**

    ```cpp
    // CPP program to illustrate
    // the array::rbegin() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // array initialisation
        array<int, 5> arr = { 1, 5, 2, 4, 7 };

        // prints the last element
        cout << "The last element is " << *(arr.rbegin()) << endl;

        // prints all the elements
        cout << "The array elements in reverse order are:\n";
        for (auto it = arr.rbegin(); it != arr.rend(); it++)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    The last element is 7
    The array elements in reverse order are:
    7 4 2 5 1

    ```

2.  **array::rend()** is a built-in function in C++ STL which returns a reverse iterator pointing to the theoretical element right before the first element in the array container.

    **语法:**

    ```cpp
    array_name.rend()
    ```

    **参数:**函数不取任何参数。

    **返回值:**函数返回一个反向迭代器，指向数组容器中第一个元素之前的理论元素。

    程序来演示数组::rend()方法:

    **程序 1:**

    ```cpp
    // CPP program to illustrate
    // the array::rend() function
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        array<int, 5> arr = { 1, 5, 2, 4, 7 };

        // prints all the elements
        cout << "The array elements in reverse order are:\n";
        for (auto it = arr.rbegin(); it != arr.rend(); it++)
            cout << *it << " ";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    The array elements in reverse order are:
    7 4 2 5 1

    ```