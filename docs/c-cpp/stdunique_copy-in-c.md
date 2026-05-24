# std::unique_copy 在 C++ 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdunique _ copy-in-c/

**[【STD::unique】](https://www.geeksforgeeks.org/stdunique-in-cpp/)**用于删除某个范围内连续出现的任何元素的重复项[第一个，最后一个]。它对连续出现相同元素的范围内的所有子组执行此任务。

但是，如果我们不想改变原来的范围，只想将 std::unique 的结果复制到另一个容器中，对此我们定义了另一个函数，即 **std::unique_copy()** 。在这种情况下，仅复制范围[第一个，最后一个]中每个连续等价元素组的第一个元素。

**有两种使用方式，如下图:**

1.  **使用==:**
    语法比较元素:

```cpp
template 
  OutputIterator unique_copy (InputIterator first, InputIterator last,
                              OutputIterator result);

first: Forward iterator to the first element in the container.
last: Forward iterator to the last element in the container.
result: Output iterator to the initial position 
of the container where the resulting range of values is stored. 
The value being pointed should be compatible with the value being assigned.

Return Value: An iterator pointing to the end 
of the copied range, which contains no consecutive duplicates.

```

```cpp
// C++ program to demonstrate 
// the use of std::unique_copy
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main()
{
    vector<int> v = { 10, 10, 30, 30, 30, 100, 10,
                      300, 300, 70, 70, 80 };

    // Declaring a vector to store the copied value
    vector<int> v1(10);

    vector<int>::iterator ip;

    // Using std::unique_copy
    ip = std::unique_copy(v.begin(), v.begin() + 12, v1.begin());
    // Now v1 contains {10 30 100 10 30 70 80 0 0 0}

    // Resizing vector v1
    v1.resize(std::distance(v1.begin(), ip));

    cout << "Before: ";
    for (ip = v.begin(); ip != v.end(); ++ ip) 
    {
        cout << *ip << " ";
    }

    // Displaying the vector after applying std::unique_copy
    cout << "\nAfter: ";
    for (ip = v1.begin(); ip != v1.end(); ++ ip) 
    {
        cout << *ip << " ";
    }

    return 0;
}
```

输出:

```cpp
Before: 10 10 30 30 30 100 10 300 300 70 70 80
After: 10 30 100 10 30 70 80 

```

这里，在该向量中，具有连续重复元素的所有子组已经被简化为仅一个元素，并且已经被复制到向量 v1。

*   **By comparing using a pre-defined function:**
    Syntax:

    ```cpp
    template 
      OutputIterator unique_copy (InputIterator first, InputIterator last,
                                  OutputIterator result, BinaryPredicate pred);

    Here, first, last and result are the same as previous case.

    Pred: Binary function that accepts two elements 
    in the range as argument, and returns a value convertible to bool. 
    The value returned indicates whether both arguments are considered equivalent
    (if true, they are equivalent and one of them is removed).
    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Return Value: It returns an iterator pointing to the 
    end of the copied range, which contains no consecutive duplicates.
    ```

    ```cpp
    // C++ program to demonstrate the 
    // use of std::unique_copy
    #include <iostream>
    #include <algorithm>
    #include <string>
    using namespace std;

    // Defining the BinaryFunction
    bool Pred(char a, char b)
    {
        // Checking if both the arguments are same and equal
        // to 'v' then only they are considered same
        // and duplicates are removed
        if (a == b && a == 'v') 
        {
            return 1;
        } 
        else 
        {
            return 0;
        }
    }
    int main()
    {
        // Declaring a string
        string s = "You arre vvvisiting GFG", s1;

        // Using std::unique_copy to remove the consecutive
        // v in the word and copy it to s1
        auto ip = std::unique_copy(s.begin(), s.end(), back_inserter(s1), Pred);

        cout << "Before: " << s;

        // Displaying the corrected string
        cout << "\nAfter: " << s1;
        return 0;
    }
    ```

    输出:

    ```cpp
    Before: You arre vvvisiting GFG
    After: You arre visiting GFG

    ```

    **哪里可以用？**

    1.  **std::unique_copy** can be used to **remove all the duplicate elements (whether consecutive or not) and store the resultant in another container**, without affecting the previous container.

        ```cpp
        // C++ program to demonstrate the use of std::unique_copy
        #include <iostream>
        #include <vector>
        #include <algorithm>
        using namespace std;
        int main()
        {
            vector<int> v = { 1, 2, 3, 3, 3, 10, 1, 2, 3, 7, 7, 8 };

            vector<int>::iterator ip;

            // Sorting the array to make duplicate elements
            // consecutive
            std::sort(v.begin(), v.end());
            // Now v becomes 1 1 2 2 3 3 3 3 7 7 8 10

            // Declaring a container to store the unique elements
            vector<int> v1(6);

            // Using std::unique_copy
            ip = std::unique_copy(v.begin(), v.begin() + 12, v1.begin());
            // Now v1 becomes {1 2 3 7 8 10}

            // Displaying the vector v and v1 after applying std::unique
            cout << "v = ";

            for (ip = v.begin(); ip != v.end(); ++ ip) 
            {
                cout << *ip << " ";
            }

            cout << "\nv1 = ";
            for (ip = v1.begin(); ip != v1.end(); ++ ip) 
            {
                cout << *ip << " ";
            }

            return 0;
        }
        ```

        输出:

        ```cpp
        v = 1 1 2 2 3 3 3 3 7 7 8 10
        v1 = 1 2 3 7 8 10

        ```

        **说明:**这里，我们首先对向量进行排序，使重复元素连续，然后应用 std::unique_copy 移除重复元素，并将唯一元素存储在另一个容器中。

    2.  We can also use std::unique_copy to **find whether a container contains only unique elements or not.** This is just an extension of the above concept of storing the unique elements in another container. After this, we can just compare the two containers to check whether they are equal or not.

        ```cpp
        // C++ program to demonstrate the use of std::unique_copy
        #include <iostream>
        #include <vector>
        #include <algorithm>
        using namespace std;
        int main()
        {
            vector<int> v = { 1, 20, 3, 10, 2, 7, 8 };

            vector<int>::iterator ip;

            // Sorting the array to make duplicate elements
            // consecutive
            std::sort(v.begin(), v.end());
            // Now v becomes 1 2 3 7 8 10 20

            // Declaring a container to store the unique elements
            vector<int> v1(7);

            // Using std::unique_copy
            ip = std::unique_copy(v.begin(), v.end(), v1.begin());
            // Now v1 becomes {1 2 3 7 8 10 20}

            if (v == v1) 
            {
                cout << "v1 contains only unique elements";
            } 
            else 
            {
                cout << "v1 contains duplicate elements";
            }
            return 0;
        }
        ```

        输出:

        ```cpp
        v1 contains only unique elements

        ```

        **解释:**首先我们去掉重复的元素，将结果存储在另一个容器中，然后将结果容器与前一个容器进行比较，如果两者相同，这意味着前一个容器只由唯一的元素组成，不存在重复的元素。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。