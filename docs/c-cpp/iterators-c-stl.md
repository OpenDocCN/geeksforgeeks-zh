# c++ STL 中的迭代器

> 原文:[https://www.geeksforgeeks.org/iterators-c-stl/](https://www.geeksforgeeks.org/iterators-c-stl/)

**先决条件:** [迭代器介绍](https://www.geeksforgeeks.org/introduction-iterators-c/)
迭代器用于指向 [STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 容器的内存地址。它们主要用于数字、字符等序列。它们降低了程序的复杂性和执行时间。

**迭代器的操作** :-

**1。begin()** :-该功能用于返回容器的**起始位置**。

**2。end()** :-该功能用于在结束位置后返回 ***。***

```cpp
// C++ code to demonstrate the working of
// iterator, begin() and end()
#include<iostream>
#include<iterator> // for iterators
#include<vector> // for vectors
using namespace std;
int main()
{
    vector<int> ar = { 1, 2, 3, 4, 5 };

    // Declaring iterator to a vector
    vector<int>::iterator ptr;

    // Displaying vector elements using begin() and end()
    cout << "The vector elements are : ";
    for (ptr = ar.begin(); ptr < ar.end(); ptr++)
        cout << *ptr << " ";

    return 0;    
}
```

**输出:**

```cpp
The vector elements are : 1 2 3 4 5 

```

**3。advance()** :-该函数用于**递增迭代器位置**，直到其参数中提到的指定数字。

```cpp
// C++ code to demonstrate the working of
// advance()
#include<iostream>
#include<iterator> // for iterators
#include<vector> // for vectors
using namespace std;
int main()
{
    vector<int> ar = { 1, 2, 3, 4, 5 };

    // Declaring iterator to a vector
    vector<int>::iterator ptr = ar.begin();

    // Using advance() to increment iterator position
    // points to 4
    advance(ptr, 3);

    // Displaying iterator position
    cout << "The position of iterator after advancing is : ";
    cout << *ptr << " ";

    return 0;

}
```

**输出:**

```cpp
The position of iterator after advancing is : 4 

```

**4。next()** :-这个函数**返回新的迭代器**，迭代器将在**推进其参数中提到的位置**之后指向该迭代器。

**5。prev()** :-这个函数**返回新的迭代器**，迭代器会在递减参数中提到的位置后指向**。**

```cpp
// C++ code to demonstrate the working of
// next() and prev() 
#include<iostream>
#include<iterator> // for iterators
#include<vector> // for vectors
using namespace std;
int main()
{
    vector<int> ar = { 1, 2, 3, 4, 5 };

    // Declaring iterators to a vector
    vector<int>::iterator ptr = ar.begin();
    vector<int>::iterator ftr = ar.end();

    // Using next() to return new iterator
    // points to 4
    auto it = next(ptr, 3);

    // Using prev() to return new iterator
    // points to 3
    auto it1 = prev(ftr, 3);

    // Displaying iterator position
    cout << "The position of new iterator using next() is : ";
    cout << *it << " ";
    cout << endl;

    // Displaying iterator position
    cout << "The position of new iterator using prev()  is : ";
    cout << *it1 << " ";
    cout << endl;

    return 0; 
}
```

**输出:**

```cpp
The position of new iterator using next() is : 4 
The position of new iterator using prev()  is : 3 

```

 **6。插入器()** :-该功能用于**将元素插入容器中的任意位置**。它接受 **2 个参数、容器和迭代器来定位必须插入元素的位置**。

```cpp
// C++ code to demonstrate the working of
// inserter()
#include<iostream>
#include<iterator> // for iterators
#include<vector> // for vectors
using namespace std;
int main()
{
    vector<int> ar = { 1, 2, 3, 4, 5 };
    vector<int> ar1 = {10, 20, 30}; 

    // Declaring iterator to a vector
    vector<int>::iterator ptr = ar.begin();

    // Using advance to set position
    advance(ptr, 3);

    // copying 1 vector elements in other using inserter()
    // inserts ar1 after 3rd position in ar
    copy(ar1.begin(), ar1.end(), inserter(ar,ptr));

    // Displaying new vector elements
    cout << "The new vector after inserting elements is : ";
    for (int &x : ar) 
        cout << x << " ";

    return 0;    
}
```

**输出:**

```cpp
The new vector after inserting elements is : 1 2 3 10 20 30 4 5 

```

**迭代器的类型:**

1.  [输入迭代器](https://www.geeksforgeeks.org/input-iterators-in-cpp/)
2.  [输出迭代器](https://www.geeksforgeeks.org/output-iterators-cpp/)
3.  [正向迭代器](https://www.geeksforgeeks.org/forward-iterators-in-cpp/)
4.  [双向迭代器](https://www.geeksforgeeks.org/bidirectional-iterators-in-cpp/)
5.  [随机访问迭代器](https://www.geeksforgeeks.org/random-access-iterators-in-cpp/)

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。