# std::is_partitioned in C++

> 原文:[https://www.geeksforgeeks.org/stdis_partitioned-in-c/](https://www.geeksforgeeks.org/stdis_partitioned-in-c/)

**std::is_partitioned** 用于查找范围【第一个，最后一个】是否分区。如果条件评估为真的所有元素都在条件评估为假的元素之前，则称该范围相对于条件被划分。

在头文件**中定义。如果我们要检查是否分区的范围是空的，那么这个函数返回 true。
语法:**

```cpp
 **bool is_partitioned (InputIterator first, 
                      InputIterator last, UnaryPredicate pred);**

**first:** Input iterator to the first element in the range.
**last:** Input iterator to the last element in the range.
**pred:** Unary function that accepts an element in the 
range as argument, and returns a value convertible to bool. 
The value returned indicates whether the element belongs to
the first group (if true, the element is expected before all
the elements for which it returns false).
The function shall not modify its argument.
This can either be a function pointer or a function object.

**Returns:** It returns true if all the elements in the range [first, last)
for which pred returns true precede those for which it returns false.
Otherwise it returns false.
If the range is empty, the function returns true. 
```

```cpp
// C++ program to demonstrate the use of std::is_partitioned
#include <iostream>
#include <algorithm>
#include <vector>

// Defining the BinaryFunction
bool pred(int a)
{
    return (a % 3 == 0);
}

using namespace std;
int main()
{
    // Declaring first vector
    vector<int> v1 = { 3, 6, 9, 10, 11, 13 };

    // Using std::is_partitioned
    bool b = std::is_partitioned(v1.begin(), v1.end(), pred);

    if (b == 1) {
        cout << "It is partitioned";
    } else {
        cout << "It is not partitioned.";
    }
    return 0;
}
```

**输出:**

```cpp
It is partitioned 
```

****说明:**这里，在这个程序中，首先我们把元素存储在一个向量中，然后我们在检查是否所有能被 3 整除的元素都出现在那些不能被 3 整除的元素之前。因为这个条件对于所取的向量来说是真的，所以这个函数在这里返回 1，因为它是分区的。**

****另一个例子****

*   ****To check whether all the odd and even elements are partitioned**

    ```cpp
    // C++ program to demonstrate the use of std::is_partitioned
    #include <iostream>
    #include <algorithm>
    #include <vector>

    // Defining the BinaryFunction
    bool pred(int a)
    {
        return (a % 2 == 0);
    }

    using namespace std;
    int main()
    {
        // Declaring first vector
        vector<int> v1 = { 2, 4, 6, 3, 5, 7, 9 };

        // Using std::is_partitioned
        bool b = std::is_partitioned(v1.begin(), v1.end(), pred);

        if (b == 1) {
            cout << "All the even no. are present before odd no.";
        } else {
            cout << "All the even no. are not present before odd no.";
        }

        // Inserting an even no. at the end of v1
        // so std::is_partitioned returns false
        v1.push_back(16);

        // Now again using std::is_partitioned
        b = std::is_partitioned(v1.begin(), v1.end(), pred);

        if (b == 1) {
            cout << "\nAll the even no. are present before odd no.";
        } else {
            cout << "\nAll the even no. are not present before odd no.";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    All the even no. are present before odd no.
    All the even no. are not present before odd no.

    ```** 

**本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**