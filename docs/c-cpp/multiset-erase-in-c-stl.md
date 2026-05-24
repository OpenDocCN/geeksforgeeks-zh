# c++ STL 中的多集擦除()

> 原文:[https://www.geeksforgeeks.org/multiset-erase-in-c-stl/](https://www.geeksforgeeks.org/multiset-erase-in-c-stl/)

**先决条件:** [多集](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)

**多集::erase()** 是 C++ 中从多集移除指定元素的 STL 函数。

这个方法有三个版本。这些是:

1.  **语法:**

```cpp
void erase (iterator position_of_iterator);

```

**参数:**该方法接受以下参数:

*   **位置 _of_iterator:** 是指需要借助迭代器移除的特定元素的位置。

**返回值:**这个方法返回被移除元素之后的迭代器。

以下示例说明了 multist::erase()方法的工作原理:

```cpp
// C++ program to demonstrate
// multiset::erase() method

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Initialise the multiset
    multiset<int> multi_set;
    multiset<int>::iterator ms_iterator;

    // Add values to the multiset
    for (int i = 1; i < 10; i++) {
        multi_set.insert(i);
    }

    cout << "Original multiset: ";

    for (ms_iterator = multi_set.begin();
         ms_iterator != multi_set.end();
         ++ ms_iterator)

        cout
            << ' ' << *ms_iterator;
    cout << '\n';

    ms_iterator = multi_set.begin();
    ms_iterator++ ;

    // Passing the iterator for the position
    // at which the value is to be erased
    multi_set.erase(ms_iterator);

    cout << "Modified multiset: ";

    for (ms_iterator = multi_set.begin();
         ms_iterator != multi_set.end();
         ++ ms_iterator)

        cout << ' ' << *ms_iterator;
    cout << '\n';

    return 0;
}
```

**Output:**

```cpp
Original multiset:  1 2 3 4 5 6 7 8 9
Modified multiset:  1 3 4 5 6 7 8 9

```

*   **Syntax:**

    ```cpp
    size_type erase (const value_type& contant_value);

    ```

    **参数:**该方法接受以下参数:

    *   **常量 _ 值**:指借助其值从多集合中移除的特定元素。它必须是恒定的。这个值的所有实例都会被这个方法删除。

    **返回值:**该方法返回被删除的值的数量。

    以下示例说明了 multist::erase()方法的工作原理:

    ```cpp
    // C++ program to demonstrate
    // multiset::erase() method

    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {

        // Initialise the multiset
        multiset<int> multi_set;

        multiset<int>::iterator ms_iterator;

        // Add values to the multiset
        for (int i = 1; i < 10; i++) {
            multi_set.insert(i);
        }

        cout << "Original multiset: ";

        for (ms_iterator = multi_set.begin();
             ms_iterator != multi_set.end();
             ++ ms_iterator)
            cout << ' ' << *ms_iterator;
        cout << '\n';

        ms_iterator = multi_set.begin();

        // Passing constant value to be erased
        int num = multi_set.erase(2);

        cout << "Modified multiset: "
             << "(" << num << ")"
             << "removed";

        for (ms_iterator = multi_set.begin();
             ms_iterator != multi_set.end();
             ++ ms_iterator)
            cout << ' ' << *ms_iterator;
        cout << '\n';

        return 0;
    }
    ```

    **Output:**

    ```cpp
    Original multiset:  1 2 3 4 5 6 7 8 9
    Modified multiset:(1)removed  1 3 4 5 6 7 8 9

    ```

    *   **Syntax:**

    ```cpp
    void erase (iterator starting_iterator, iterator ending_iterator);

    ```

    **参数:**该方法接受以下参数:

    *   **starting_iterator** :指要从多集合中移除的值范围的起始迭代器。
    *   **end _ iterator**:是指要从多集合中移除的值范围的结束迭代器。

    **返回值:**这个方法返回最后一个移除的元素之后的迭代器或者结束迭代器。

    以下示例说明了 multist::erase()方法的工作原理:

    ```cpp
    // C++ program to demonstrate
    // multiset::erase() method

    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {

        // Initialise the multiset
        multiset<int> multi_set;
        multiset<int>::iterator ms_iterator;

        // Add values to the multiset
        for (int i = 1; i < 10; i++) {
            multi_set.insert(i);
        }

        cout << "Original multiset: ";

        for (ms_iterator = multi_set.begin();
             ms_iterator != multi_set.end();
             ++ ms_iterator)

            cout << ' ' << *ms_iterator;
        cout << '\n';

        ms_iterator = multi_set.begin();
        ms_iterator++ ;
        ms_iterator++ ;

        // Passing the iterator range for the positions
        // at which the values are to be erased
        auto ir = multi_set.erase(ms_iterator, multi_set.end());

        cout << "Modified multiset: ";

        for (ms_iterator = multi_set.begin();
             ms_iterator != multi_set.end();
             ++ ms_iterator)

            cout << ' ' << *ms_iterator;
        cout << '\n';
        (ir == multi_set.end())
            ? cout << "Return value is: multi_set.end()\n "
            : cout
                  << "Return value is not multi_set.end()\n";

        return 0;
    }
    ```

    **Output:**

    ```cpp
    Original multiset:  1 2 3 4 5 6 7 8 9
    Modified multiset:  1 2
    Return value is: multi_set.end();

    ```