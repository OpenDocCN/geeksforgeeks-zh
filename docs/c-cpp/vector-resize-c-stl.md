# 矢量: :在 C++ STL 中调整大小()

> 原文:[https://www.geeksforgeeks.org/vector-resize-c-stl/](https://www.geeksforgeeks.org/vector-resize-c-stl/)

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)被称为动态数组，当元素被插入或删除时，它可以自动改变其大小。该存储由容器维护。

**vector::resize()**

该函数通过插入或删除容器中的元素来实际改变容器的内容。事情就是这样，

*   如果给定的 n 值小于当前的大小，则拆除额外的元素。
*   如果 n 大于容器的当前大小，那么即将到来的元素将被附加到向量的末尾。

**语法:**

```cpp
*vectorname*.resize(int n, int val)

```

> **参数:**
> 
> *   ***n***–是新容器尺寸，用元素数量表示。*   ***val*** – if this parameter is specified then new elements are initialized with this value.
>     
>     **返回值:**
>     
>     *   This function do not returns anything.
>     
>     例外:
>     
>     *   如果发生这种情况，唯一的例外是如果重新分配失败，抛出 [Bad_alloc](https://www.geeksforgeeks.org/bad_alloc-in-cpp/) 。

下面的程序说明了该功能的工作原理

2.  **Size of the vector container is lowered.

    ```cpp
    // resizing of the vector
    #include <iostream>
    #include <vector>

    using namespace std;

    int main()
    {
        vector<int> vec;

        // 5 elements are inserted
        // in the vector
        vec.push_back(1);
        vec.push_back(2);
        vec.push_back(3);
        vec.push_back(4);
        vec.push_back(5);

        cout << "Contents of vector before resizing:" 
             << endl;

        // displaying the contents of the
        // vector before resizing
        for (int i = 0; i < vec.size(); i++)
            cout << vec[i] << " ";

        cout << endl;

        // vector is resized
        vec.resize(4);

        cout << "Contents of vector after resizing:" 
             << endl;

        // displaying the contents of the
        // vector after resizing
        for (int i = 0; i < vec.size(); i++)
            cout << vec[i] << " ";

        return 0;
    }
    ```

    输出:

    ```cpp
    Contents of the vector before resizing:
    1 2 3 4 5 
    Contents of the vector after resizing:
    1 2 3 4 

    ```** 
3.  ****Size of the vector container is increased.

    ```cpp
    // resizing of the vector
    #include <iostream>
    #include <vector>

    using namespace std;

    int main()
    {
        vector<int> vec;

        // 5 elements are inserted 
        // in the vector
        vec.push_back(1);
        vec.push_back(2);
        vec.push_back(3);
        vec.push_back(4);
        vec.push_back(5);

        cout << "Contents of vector before resizing:" 
             << endl;

        // displaying the contents of the
        // vector before resizing
        for (int i = 0; i < vec.size(); i++)
            cout << vec[i] << " ";

        cout << endl;

        // vector is resized
        vec.resize(8);

        cout << "Contents of vector after resizing:" 
             << endl;

        // displaying the contents of 
        // the vector after resizing
        for (int i = 0; i < vec.size(); i++)
            cout << vec[i] << " ";

        return 0;
    }
    ```

    输出:

    ```cpp
    Contents of the vector before resizing:
    1 2 3 4 5 
    Contents of the vector after resizing:
    1 2 3 4 5 0 0 0 

    ```**** 
4.  ******Size of the vector container is increased and new elements are initialized with specified value.

    ```cpp
    // resizing of the vector
    #include <iostream>
    #include <vector>

    using namespace std;

    int main()
    {
        vector<int> vec;

        // 5 elements are inserted
        // in the vector
        vec.push_back(1);
        vec.push_back(2);
        vec.push_back(3);
        vec.push_back(4);
        vec.push_back(5);

        cout << "Contents of vector before resizing:"
             << endl;

        // displaying the contents of 
        // the vector before resizing
        for (int i = 0; i < vec.size(); i++)
            cout << vec[i] << " ";

        cout << endl;

        // vector is resized
        vec.resize(12, 9);

        cout << "Contents of vector after resizing:" 
             << endl;

        // displaying the contents 
        // of the vector after resizing
        for (int i = 0; i < vec.size(); i++)
            cout << vec[i] << " ";

        return 0;
    }
    ```

    输出:

    ```cpp
    Contents of the vector before resizing:
    1 2 3 4 5 
    Contents of the vector after resizing:
    1 2 3 4 5 9 9 9 9 9 9 9 

    ```******