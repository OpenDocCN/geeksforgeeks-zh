# STD::rotate vs . STD::rotate _ copy 在 C++ STL 中

> 原文:[https://www . geesforgeks . org/stdrotate-vs-stdrotate _ copy-c-STL/](https://www.geeksforgeeks.org/stdrotate-vs-stdrotate_copy-c-stl/)

1.  **rotate in STL**:It rotates the order of the elements in the range [first, last), in such a way that the element pointed by middle becomes the new first element, i, e, to the left.

    ```cpp
    // Illustrating the use of rotate algorithm
    #include <bits/stdc++.h>
    using namespace std;

    // Driver Program
    int main()
    {
        vector<int> arr;

        // set some values: 1 2 3 4 5 6
        // 7 8 9
        for (int i = 1; i < 10; ++ i)        
            arr.push_back(i);

        // Use of rotate
        rotate(arr.begin(), arr.begin() + 3, arr.end());

        // prints the content:
        cout << "arr contains:";
        for (auto i = arr.begin(); i != arr.end(); i++)
            cout << ' ' << *i;
        cout << endl;

        return 0;
    }
    ```

    输出:

    ```cpp
    arr contains: 4 5 6 7 8 9 1 2 3

    ```

2.  **rotate_copy** :它将范围[第一个，最后一个]中的元素复制到从结果开始的范围，但是旋转元素的顺序，使中间指向的元素成为结果范围中的第一个元素，即向左旋转。

    ```cpp
    // Illustrating the use of rotate_copy
    #include <bits/stdc++.h>
    using namespace std;

    // Driver Program
    int main()
    {
        int arr[] = { 10, 20, 30, 40, 50, 60, 70 };    

        // Use of rotate_copy
        vector<int> gfg(7);
        rotate_copy(arr, arr + 3, arr + 7, gfg.begin());

        // prints the content:
        cout << "gfg contains:";
        for (auto i = gfg.begin(); i != gfg.end(); i++)
            cout << ' ' << *i;
        cout << endl;

        return 0;
    }
    ```

    输出:

    ```cpp
    gfg contains: 40 50 60 70 10 20 30

    ```

本文由**香巴拉维·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。