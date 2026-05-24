# c++ STL 中的向量插入()函数

> 原文:[https://www . geesforgeks . org/vector-insert-function-in-c-STL/](https://www.geeksforgeeks.org/vector-insert-function-in-c-stl/)

**std::vector::insert()** 是 C++ STL 中的内置函数，在指定位置的元素前插入新元素，通过插入的元素数量有效增加容器大小。

1.  **Syntax:**

    ```cpp
    vector_name.insert (position, val)

    ```

    **参数:**该函数接受如下指定的两个参数:

    *   *位置–*它指定迭代器，该迭代器指向要进行插入的位置。
    *   *val–*指定要插入的值。

    **返回值:**函数返回一个迭代器，指向新插入的元素。

    **示例 1:** 下面的程序说明了上述功能，其中新元素被插入到前面。

    ```cpp
    // Program below illustrates the
    // vector::insert() function

    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // initialising the vector
        vector<int> vec = { 10, 20, 30, 40 };

        // inserts 3 at front
        auto it = vec.insert(vec.begin(), 3);
        // inserts 2 at front
        vec.insert(it, 2);

        int i = 2;
        // inserts 7 at i-th index
        it = vec.insert(vec.begin() + i, 7);

        cout << "The vector elements are: ";
        for (auto it = vec.begin(); it != vec.end(); ++ it)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    The vector elements are: 2 3 7 10 20 30 40

    ```

    **示例 2:** 下面的程序说明了上述功能，其中新元素被插入到特定位置。

    ```cpp
    // Program below illustrates the
    // vector::insert() function

    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // initialising the vector
        vector<int> vec = { 10, 20, 70, 80 };
        int x = 50;

        // inserting multiple elements
        // at specific positions
        vec.insert(vec.begin() + 2, { 30, 40, x, 60 });

        cout << "The vector elements are: ";
        for (auto it : vec)
            cout << it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    The vector elements are: 10 20 30 40 50 60 70 80

    ```

2.  **Syntax:**

    ```cpp
    vector_name.insert(position, size, val)

    ```

    **参数:**该函数接受如下指定的三个参数:

    *   *位置–*它指定迭代器，该迭代器指向要进行插入的位置。
    *   *size–*指定在指定位置插入 val 的次数。
    *   *val–*指定要插入的值。

    **返回值:**函数返回一个迭代器，指向新插入的元素。

    下面的程序说明了上述功能:

    ```cpp
    // program below illustrates the
    // vector::insert() function

    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // initialising the vector
        vector<int> vec = { 10, 20, 30, 40 };

        // inserts 3 one time at front
        auto it = vec.insert(vec.begin(), 1, 3);

        // inserts 4 two times at front
        vec.insert(it, 2, 4);

        cout << "The vector elements are: ";
        for (auto it = vec.begin(); it != vec.end(); ++ it)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    The vector elements are: 4 4 3 10 20 30 40

    ```

3.  **Syntax:**

    ```cpp
    vector_name.insert(position, iterator1, iterator2)

    ```

    **参数:**该函数接受如下指定的三个参数:

    *   *位置–*指定向量中插入的位置。
    *   *迭代器 1–*指定元素插入的起始位置
    *   *迭代器 2–*它指定要插入元素的结束位置

    **返回值:**函数返回一个迭代器，指向新插入的元素。

    以下是上述功能的图示:

    ```cpp
    // program below illustrates the
    // vector::insert() function

    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // initialising the vector
        vector<int> vec1 = { 10, 20, 30, 40 };
        vector<int> vec2;

        // inserts at the beginning of vec2
        vec2.insert(vec2.begin(), vec1.begin(), vec1.end());

        cout << "The vector2 elements are: ";
        for (auto it = vec2.begin(); it != vec2.end(); ++ it)
            cout << *it << " ";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    The vector2 elements are: 10 20 30 40

    ```