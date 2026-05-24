# 有序集和 GNU C++ PBDS

> 原文:[https://www.geeksforgeeks.org/ordered-set-gnu-c-pbds/](https://www.geeksforgeeks.org/ordered-set-gnu-c-pbds/)

**先决条件**:[STL 基础知识](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/)、[设置数据结构](https://www.geeksforgeeks.org/set-in-cpp-stl/)。

**<u>约订集</u>**

有序集是 g++ 中基于[策略的数据结构，它将**唯一的**元素保持在有序的顺序中。它以 log(n)复杂度执行 STL 中集合数据结构执行的所有操作，并以 log(n)复杂度执行两个附加操作。](https://www.geeksforgeeks.org/policy-based-data-structures-g/)

*   **order_of_key (k)** :严格小于 k 的项目数。
*   **find_by_order(k)** :集合中的第 K 个元素(从零开始计数)。

**<u>实现有序集所需的头文件及其描述</u>**

为了实现有序集，GNU C++ 库包含其他基于策略的数据结构，我们需要包括:

> *   //我叫吴登盛，我叫吴登盛，我叫吴登盛，我叫吴登盛，我叫吴登盛，我叫吴登盛，我叫吴登盛，我叫吴登盛，我叫吴登盛，我叫吴登盛
>     **哎哎哎< ext/Pb _ ds/assoc _ container。HPP >***   //包含树 _ 序 _ 统计 _ 节点 _ 更新
>     **包含< ext/Pb _ ds/tree _ policy。>HPP**

第一个用于包含关联容器或模板组，如集合、多地图、地图等。我们将在下面使用的基于树的数据结构出现在这个头文件中。
第二个头文件用于包含*树 _ 订单 _ 统计 _ 节点更新*，解释如下:

```cpp
using namespace __gnu_pbds;

```

这是基于 **GNU 策略的数据结构**所必需的名称空间。

基于树的容器具有具体的结构，但是有序集实现所需的必要结构是:

```cpp
tree < int ,  null_type ,  less ,  rb_tree_tag ,  tree_order_statistics_node_update >

```

1.  **int** :是我们要插入的数据的类型(KEY)。它可以是整数、浮点或整数对等。
2.  **null_type** :是映射的策略。这里使用它作为集合是空的。如果我们想得到映射而不是集合，作为第二个参数类型必须使用映射类型。
3.  **少**:是两个功能比较的基础。
4.  **rb_tree_tag** :使用的树的类型。它通常是红黑树，因为插入和删除需要 log(n)时间，而其他树则需要线性时间，如 splay _ tree。
5.  **tree _ order _ statistics _ node _ update**:包含在 tree_policy.hpp 中，包含了更新基于树的容器的节点变体的各种操作，所以我们可以跟踪像一个子树中的节点数量这样的元数据

**有序集合中除集合**以外的附加功能

连同机组之前的操作，支持*两个*主要重要操作

*   **find_by_order(k)** :返回到 0(logn)时间集合中第 kth 元素**(从零开始计数)**的迭代器。要找到第一个元素，k 必须为零。
    假设我们有一个集合 s : {1，5，6，17，88}，然后:
    *(s.find_by_order(2)):集合中的第三个元素，即 6
    *(s.find_by_order(4)):集合中的第五个元素，即 88
*   **order_of_key(k)** :返回 O(logn)时间内**严格来说**比我们的物品 k 小的物品数量。
    假设我们有一组 s : {1，5，6，17，88}，那么:
    s.order_of_key(6):元素计数**严格来说**小于 6 就是 2。
    s.order_of_key(25):小于 25 的元素数**严格来说**为 4。

**集合和有序集合的区别**
集合和有序集合之间没有太大的区别，尽管有序集合可以被假设为集合的扩展版本，能够执行一些在竞争性编程中广泛使用的更高级的功能(如上所述)。

* * *

**NOTE** : **<u>ordered_set</u>** is used here as a macro given to *tree<int, null_type, less, rb_tree_tag, tree_order_statistics_node_update>.* Therefore it can be given any name as *macro* other than ordered_set but generally in the world of competitive programming it is commonly referred as ordered set as it is a set with additional operations.

* * *

**实际应用:**
假设我们有一种情况，在一个数组中一个接一个地插入元素，每次插入后，我们都被赋予一个范围[l，r]，我们必须确定数组中大于等于 l 且小于等于 r 的元素个数，最初，数组是空的。
示例:

```cpp
Input :    5
           1 2
           1
           2 5
           2
           1 5

Output :   0
           1
           3

```

**说明:**

*   插入了 5。*   大于等于 1 且小于等于 2 的元素计数为 0。*   已插入 1。*   大于等于 2 且小于等于 5 的元素计数为 1，即 5。*   插入了 2。*   大于等于 1 且小于等于 5 的元素计数为 3，即 5、1、2。

    ```cpp
    Input :     1
                1 2
                2
                3 5
                5
                1 4
    Output :    1
                0
                2

    ```

    最初，数组是空的

    *   已插入 1。
    *   大于等于 1 且小于等于 2 的元素计数为 1，即 1。
    *   插入了 2。
    *   大于等于 3 且小于等于 5 的元素计数为 0。
    *   插入了 5。
    *   Count of elements greater than equal to 1 and less than equal to 4 is 2 i.e. 1, 2.

        如果我们在 STL 中使用 STL find upper _ bound on set，它只给出元素的地址，我们只能通过使用解引用运算符(*)找到该地址的值。

        假设我们有一个集合为{0，1，2，7，8，20}并且我们找到了 2 的 upper_bound，那么它会返回一个对应于集合中元素(本例中为 7)位置的地址，并且我们**不能**减去集合的起始地址(s.begin())来找到小于 2 的元素数量，就像向量的情况一样。
        那么，有序集合的需求来了。

        **<u>注</u> :** 上述功能可以借助其他一些逻辑和数据结构来实现，但有序集的使用使代码紧凑，可以轻松快速地实现。

        **有序集的实现**

        ```cpp
        // C++ program to demonstrate the
        // ordered set in GNU C++
        #include <iostream>
        using namespace std;

        // Header files, namespaces,
        // macros as defined above
        #include <ext/pb_ds/assoc_container.hpp>
        #include <ext/pb_ds/tree_policy.hpp>
        using namespace __gnu_pbds;

        #define ordered_set tree<int, null_type,less<int>, rb_tree_tag,tree_order_statistics_node_update>

        // Driver program to test above functions
        int main()
        {
            // Ordered set declared with name o_set
            ordered_set o_set;

            // insert function to insert in
            // ordered set same as SET STL
            o_set.insert(5);
            o_set.insert(1);
            o_set.insert(2);

            // Finding the second smallest element
            // in the set using * because
            //  find_by_order returns an iterator
            cout << *(o_set.find_by_order(1)) 
                 << endl;

            // Finding the number of elements
            // strictly less than k=4
            cout << o_set.order_of_key(4) 
                 << endl;

            // Finding the count of elements less 
            // than or equal to 4 i.e. strictly less
            // than 5 if integers are present
            cout << o_set.order_of_key(5) 
                 << endl;

            // Deleting 2 from the set if it exists
            if (o_set.find(2) != o_set.end())
                o_set.erase(o_set.find(2));

            // Now after deleting 2 from the set
            // Finding the second smallest element in the set
            cout << *(o_set.find_by_order(1)) 
                 << endl;

            // Finding the number of
            // elements strictly less than k=4
            cout << o_set.order_of_key(4) 
                 << endl;

            return 0;
        }
        ```

        输出

        ```cpp
        2
        2
        2
        5
        1

        ```

        因此，我们现在可以很容易地解决上述问题，即 l 和 r 之间的元素计数可以通过:
        o _ set . order _ of _ key(r+1)–o _ set . order _ of _ key(l)找到

        **注**:由于集合只包含 **UNIQUE** 元素，所以要对有重复元素的数组进行运算，我们可以将 KEY 作为一对元素，而不是整数，其中第一个元素是数组中我们需要的元素，只有第二个元素必须是唯一的，这样整个对才是唯一的。

        详见:
        **<u>https://gcc . GNU . org/online docs/libstdc++/manual/policy _ data _ structures . html</u>**