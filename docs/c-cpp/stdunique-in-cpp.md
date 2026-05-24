# std::在 C++ 中独一无二

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stdunique-in-CPP/

**std::unique** 用于删除某个范围内连续出现的任何元素的重复项[第一个，最后一个]。它对连续出现相同元素的范围内的所有子组执行此任务。

*   它不会删除所有重复的元素，但它会通过用序列中的下一个元素替换这些元素来消除重复，该元素与被替换的当前元素不重复。所有被替换的元素都处于**未指定状态。**
*   这个函数的另一个有趣的特性是**它不改变容器的大小**在删除元素后，它只是返回一个指向容器新端的指针，基于此我们必须调整容器的大小，或者删除垃圾元素。

**有两种使用方式，如下图:**

1.  **Comparing elements using ==:**
    Syntax:

    ```cpp
    template 
    ForwardIterator unique (ForwardIterator first, ForwardIterator last);

    first: Forward iterator to the first element in the container.
    last: forward iterator to the last element in the container.

    Return Value: It returns an iterator to the element that follows 
    the last element not removed. The range between first and this iterator includes 
    all the elements in the sequence that were not
    duplicates and hence not removed.

    ```

    ```cpp
    // C++ program to demonstrate the use of std::unique
    #include <iostream>
    #include <vector>
    #include <algorithm>
    using namespace std;
    int main()
    {
        vector<int> v = { 1, 1, 3, 3, 3, 10, 1, 3, 3, 7, 7, 8 }, i;

        vector<int>::iterator ip;

        // Using std::unique
        ip = std::unique(v.begin(), v.begin() + 12);
        // Now v becomes {1 3 10 1 3 7 8 * * * * *}
        // * means undefined

        // Resizing the vector so as to remove the undefined terms
        v.resize(std::distance(v.begin(), ip));

        // Displaying the vector after applying std::unique
        for (ip = v.begin(); ip != v.end(); ++ ip) {
            cout << *ip << " ";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    1 3 10 1 3 7 8

    ```

    这里，在该向量中，具有连续重复元素的所有子组已经被简化为仅一个元素。请注意，稍后是否出现相同的元素并不重要，这个函数只处理连续出现的重复元素。

2.  **By comparing using a pre-defined function:**
    Syntax:

    ```cpp
    template 
     ForwardIterator unique (ForwardIterator first, ForwardIterator last,
                             BinaryPredicate Pred);

    Here, first and last are the same as previous case.

    Pred: Binary function that accepts two elements 
    in the range as argument, and returns a value convertible to bool. 
    The value returned indicates whether both arguments are considered equivalent
    (if true, they are equivalent and one of them is removed).
    The function shall not modify any of its arguments.
    This can either be a function pointer or a function object.

    Return Value: It returns an iterator to the element that 
    follows the last element not removed.
    The range between first and this iterator includes 
    all the elements in the sequence that were not
    duplicates and hence not removed.
    ```

    ```cpp
    // C++ program to demonstrate the use of std::unique
    #include <iostream>
    #include <algorithm>
    #include <string>
    using namespace std;

    // Defining the BinaryFunction
    bool Pred(char a, char b)
    {
        // Checking if both the arguments are same and equal
        // to 'G' then only they are considered same
        // and duplicates are removed
        if (a == b && a == 'G') {
            return 1;
        } else {
            return 0;
        }
    }
    int main()
    {
        // Declaring a string
        string s = "You arre vvvisiting GGGGFGGGG";

        // Using std::unique to remove the consecutive
        // G in the word
        auto ip = std::unique(s.begin(), s.end(), Pred);

        // Displaying the corrected string
        cout << string(s.begin(), ip);
        return 0;
    }
    ```

    输出:

    ```cpp
    You arre vvvisiting GFG

    ```

    在这里，我们对二进制函数进行了这样的操作:只有当两个 G 作为参数传递时，它们才会被认为是相同的，如果任何其他字符连续出现，那么它将不受影响，并且不会被移除(就像 arre 中的 r，visiting 中的 v)。

**可以使用 str::unique 的地方？**

1.  **Remove all the duplicate elements from a container:** Many of you must have searched for std::unique with a view that it will remove all the duplicate elements from the container, and now you might feel a bit disappointed to know that it removes only the consecutive duplicate elements. But, although, **std::unique** cannot do so as per its definition, but applying a bit of logic, we can make that happen. What we need to do is just sort the array before applying std::unique, such that all equal elements become consecutive, and now we have std::unique to remove all the duplicate consecutive elements.

    所以，std::unique 也可以用来**移除容器中所有重复的元素。**

    ```cpp
    // C++ program to demonstrate the use of std::unique
    #include <iostream>
    #include <vector>
    #include <algorithm>
    using namespace std;
    int main()
    {
        vector<int> v = { 1, 2, 3, 3, 3, 10, 1, 2, 3, 7, 7, 8 };

        vector<int>::iterator ip;

        // Sorting the array
        std::sort(v.begin(), v.end());
        // Now v becomes 1 1 2 2 3 3 3 3 7 7 8 10

        // Using std::unique
        ip = std::unique(v.begin(), v.begin() + 12);
        // Now v becomes {1 2 3 7 8 10 * * * * * *}
        // * means undefined

        // Resizing the vector so as to remove the undefined terms
        v.resize(std::distance(v.begin(), ip));

        // Displaying the vector after applying std::unique
        for (ip = v.begin(); ip != v.end(); ++ ip) {
            cout << *ip << " ";
        }

        return 0;
    }
    ```

    输出:

    ```cpp
    1 2 3 7 8 10

    ```

    **解释:**首先，我们对数组进行排序，使得所有相等的重复元素都变成连续的，现在对其应用 std::unique，从而消除重复，这样我们就从容器中移除了所有重复元素，无论是否连续。

2.  **Count unique elements :** It can also be used if we want to count the total no. of unique elements in a container.

    ```cpp
    // C++ program to demonstrate the use of std::unique
    #include <iostream>
    #include <iterator>
    #include <vector>
    #include <algorithm>
    using namespace std;
    int main()
    {
        vector<int> v = { 1, 1, 3, 3, 3, 10, 1, 3, 3, 7, 7, 8 };

        vector<int>::iterator ip;

        int count;
        sort(v.begin(), v.end());

        // Using std::unique and std::distance to count
        // unique elements in a container
        count = std::distance(v.begin(),
                              std::unique(v.begin(), v.begin() + 12));

        // Displaying the value of count
        cout << "Total no. of unique elements = " << count;

        return 0;
    }
    ```

    输出:

    ```cpp
    Total no. of unique elements = 5

    ```

    **解释:**由于我们知道 std::unique 在移除重复元素后会返回一个迭代器到容器的新结尾应该是什么，所以仅仅是在 std::distance 的帮助下计算从开始到这个新结尾的元素总数，应该就能给出容器中唯一元素的总数。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。