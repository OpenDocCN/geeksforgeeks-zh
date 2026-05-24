# 如何在 C++ 中不用迭代器迭代一个向量

> 原文:[https://www . geeksforgeeks . org/如何在不使用 c-iterators 的情况下迭代向量/](https://www.geeksforgeeks.org/how-to-iterate-through-a-vector-without-using-iterators-in-c/)

**先决条件:**[c++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/)[c++ STL 中的迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)

迭代器不是迭代任何 [STL 容器](https://www.geeksforgeeks.org/containers-cpp-stl/)的唯一方法。有一种更好更有效的方法可以不用迭代器迭代向量。它可以使用存储在任何容器中的值进行迭代。以下是向量的语法:

**语法:**

```cpp
for(auto itr : vector_name)

```

**说明:**这里 **itr** 是存储在向量中的值，用于遍历向量。下面是同样的程序来说明:

```cpp
// C++ program to illustrate the above
// topic
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{

    // Declare the vector
    vector<int> arr = { 1, 2, 3, 4 };

    // Traversing the vector using
    // values directly
    for (auto& it : arr) {

        // Print the values
        cout << it << ' ';
    }
    return 0;
}
```

**Output:**

```cpp
1 2 3 4

```

**更新向量中的值:**用于在不使用迭代器的情况下更新向量中的值，使用引用遍历存储在向量中的值并更新该值。下面是相同的语法:

**语法:**

```cpp
for(auto &itr : vector_name)

```

**说明:**这里 **itr** 是存储在向量中的值的地址，用于遍历向量。下面是同样的程序来说明:

```cpp
// C++ program to illustrate the updation
// in vector without using iterator
#include <bits/stdc++.h>
using namespace std;

// Function to update the value in vector
void updateVector(vector<int> arr)
{

    cout << "Vector Before Update: ";
    for (auto& it : arr) {
        cout << it << ' ';
    }

    // Traverse using the reference to value
    // and multiply each value by 2
    for (auto& it : arr) {
        it *= 2;
    }

    cout << "\nVector After Update: ";
    // Print vector elements
    for (auto& it : arr) {
        cout << it << ' ';
    }
}

// Driver Code
int main()
{

    // Declare the vector
    vector<int> arr = { 1, 2, 3, 4 };

    // Function Call
    updateVector(arr);
    return 0;
}
```

**Output:**

```cpp
Vector Before Update: 1 2 3 4 
Vector After Update: 2 4 6 8

```

**优势:**

*   简单易写的代码。
*   比使用迭代器方法更好更有效。

**缺点:**

*   它只向前迭代。
*   不保留计数器，也就是说，我们无法通过遍历找到任何元素的索引。为了对元素进行计数，计数器必须显式取值。

我们也可以在 C++ 中的许多不同[容器中使用相同的遍历进行迭代。以下是相同的插图:](https://www.geeksforgeeks.org/containers-cpp-stl/)

1.  **地图:**

    ```cpp
    // C++ program to illustrate the iteration
    // in Map without using iterator
    #include <bits/stdc++.h>
    using namespace std;

    // Driver Code
    int main()
    {

        // Declare the map
        map<int, int> Mp;

        // Inserting values in Map
        Mp[1] = 1;
        Mp[2] = 2;
        Mp[3] = 3;

        // Iterate using value in Map
        for (auto it : Mp) {

            // Print the elements
            cout << it.first << ' '
                 << it.second << endl;
        }

        return 0;
    }
    ```

    **输出:**

    ```cpp
    1 1
    2 2
    3 3

    ```

2.  **矢量地图:**

    ```cpp
    // C++ program to illustrate the iteration
    // in Map of vectors without using iterator
    #include <bits/stdc++.h>
    using namespace std;

    // Driver Code
    int main()
    {

        // Declare the map of vectors
        map<int, vector<int> > Mp;

        // Temporary vector
        vector<int> temp = { 1, 2, 3 };

        // Inserting values in Map
        Mp[1] = temp;

        temp = { 2, 3, 8, 9 };
        Mp[2] = temp;

        temp = { 10, -2 };
        Mp[3] = temp;

        // Iterate using value in Map of vectors
        for (auto it : Mp) {

            // Print the elements
            cout << it.first << " -> ";

            // Traverse each vector map
            // with it.first and print the
            // elements
            for (auto jt : it.second) {
                cout << jt << ' ';
            }

            cout << endl;
        }

        return 0;
    }
    ```

    **输出:**

    ```cpp
    1 -> 1 2 3 
    2 -> 2 3 8 9 
    3 -> 10 -2

    ```

3.  **设定:**

    ```cpp
    // C++ program to illustrate the iteration
    // in set without using iterator
    #include <bits/stdc++.h>
    using namespace std;

    // Driver Code
    int main()
    {

        // Declare the set
        set<int> S;

        // Inserting values in set
        S.insert(3);
        S.insert(-1);
        S.insert(3);
        S.insert(4);

        // Iterate using value in set
        for (auto it : S) {

            // Print the elements
            cout << it << ' ';
        }
        return 0;
    }
    ```

    **输出:**

    ```cpp
    -1 3 4

    ```

4.  **Deque:**

    ```cpp
    // C++ program to illustrate the iteration
    // in deque without using iterator
    #include <bits/stdc++.h>
    using namespace std;

    // Driver Code
    int main()
    {

        // Declare the deque
        deque<int> dq;

        // Inserting values in deque
        dq.push_front(1);
        dq.push_front(2);
        dq.push_front(3);

        dq.push_back(4);
        dq.push_back(5);
        // Iterate using value in set
        for (auto it : dq) {

            // Print the elements
            cout << it << ' ';
        }
        return 0;
    }
    ```

    **输出:**

    ```cpp
    3 2 1 4 5

    ```