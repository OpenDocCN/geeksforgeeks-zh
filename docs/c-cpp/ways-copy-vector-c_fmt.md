# 在 C++ 中复制向量的方法

> 原文：[https://www.geeksforgeeks.org/ways-copy-vector-c/](https://www.geeksforgeeks.org/ways-copy-vector-c/)

在数组的情况下，除了迭代方法（即运行循环来复制各自索引处的每个元素）之外，没有太多选择来将数组复制到其他数组中。但是向量类有不止一种方法可以更容易地将整个向量复制到其他类中。基本上有两种类型的复制。

## 方法一：迭代法

这个方法是一个通用的复制方法，在这个方法中一个循环被用来 `push_back()` 把旧的向量元素变成新的向量。它们被深深地复制。

```cpp
// C++ code to demonstrate copy of vector
// by iterative method.
#include<iostream>
#include<vector>
using namespace std;

int main()
{
    // Initializing vector with values
    vector<int> vect1{1, 2, 3, 4};

    // Declaring new vector
    vector<int> vect2;

    // A loop to copy elements of
    // old vector into new vector
    // by Iterative method
    for (int i=0; i<vect1.size(); i++)
        vect2.push_back(vect1[i]);

    cout << "Old vector elements are : ";
    for (int i=0; i<vect1.size(); i++)
        cout << vect1[i] << " ";
    cout << endl;

    cout << "New vector elements are : ";
    for (int i=0; i<vect2.size(); i++)
        cout << vect2[i] << " ";
    cout<< endl;

    // Changing value of vector to show that a new
    // copy is created.
    vect1[0] = 2;

    cout << "The first element of old vector is :";
    cout << vect1[0] << endl;
    cout << "The first element of new vector is :";
    cout << vect2[0] <<endl;

    return 0;
}
```

输出：

```cpp
Old vector elements are : 1 2 3 4 
New vector elements are : 1 2 3 4 
The first element of old vector is : 2
The first element of new vector is : 1
```

在上面的代码中，改变一个向量的值不会改变另一个向量的值，因此它们不会被分配到相同的地址，因此是深度复制。

## 方法二：由赋值 `=` 运算符

简单地将新向量分配给旧向量，复制向量。在数组的情况下，这种赋值方式是不可能的。

```cpp
// C++ code to demonstrate copy of vector
// by iterative method.
#include<iostream>
#include<vector>
using namespace std;

int main()
{
    // Initializing vector with values
    vector<int> vect1{1, 2, 3, 4};

    // Declaring new vector
    vector<int> vect2;

    // Using assignment operator to copy one
    // vector to other
    vect2 = vect1;

    cout << "Old vector elements are : ";
    for (int i=0; i<vect1.size(); i++)
        cout << vect1[i] << " ";
    cout << endl;

    cout << "New vector elements are : ";
    for (int i=0; i<vect2.size(); i++)
        cout << vect2[i] << " ";
    cout<< endl;

    // Changing value of vector to show that a new
    // copy is created.
    vect1[0] = 2;

    cout << "The first element of old vector is :";
    cout << vect1[0] << endl;
    cout << "The first element of new vector is :";
    cout << vect2[0] <<endl;

    return 0;
}
```

输出：

```cpp
Old vector elements are : 1 2 3 4 
New vector elements are : 1 2 3 4 
The first element of old vector is : 2
The first element of new vector is : 1
```

## 方法三：通过传递向量作为构造函数

在声明向量时，传递一个旧的初始化向量，将传递的向量的元素复制到新声明的向量中。它们被深深地复制。

```cpp
// C++ code to demonstrate copy of vector
// by constructor method.
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // Initializing vector with values
    vector<int> vect1{1, 2, 3, 4};

    // Declaring new vector and copying
    // element of old vector
    // constructor method, Deep copy
    vector<int> vect2(vect1);

    cout << "Old vector elements are : ";
    for (int i=0; i<vect1.size(); i++)
        cout << vect1[i] << " ";
    cout << endl;

    cout << "New vector elements are : ";
    for (int i=0; i<vect2.size(); i++)
        cout << vect2[i] << " ";
    cout<< endl;

    // Changing value of vector to show that a new
    // copy is created.
    vect1[0] = 2;

    cout << "The first element of old vector is :";
    cout << vect1[0] << endl;
    cout << "The first element of new vector is :";
    cout << vect2[0] <<endl;

    return 0;
}
```

输出：

```cpp
Old vector elements are : 1 2 3 4 
New vector elements are : 1 2 3 4 
The first element of old vector is :2
The first element of new vector is :1
```

## 方法四：使用内置功能

*   **`copy(first_iterator_o, last_iterator_o, back_inserter())`**：这是另一种将旧向量复制到新向量的方法。此函数接受 3 个参数，第一个是旧向量的起始迭代器，第二个是旧向量的结束迭代器，第三个是 `back_inserter` 函数，用于从尾部插入值。这也生成一个深拷贝。

```cpp
// C++ code to demonstrate copy of vector
// by assign() and copy().
#include<iostream>
#include<vector> // for vector
#include<algorithm> // for copy() and assign()
#include<iterator> // for back_inserter
using namespace std;
int main()
{
    // Initializing vector with values
    vector<int> vect1{1, 2, 3, 4};

    // Declaring new vector
    vector<int> vect2;

    // Copying vector by copy function
    copy(vect1.begin(), vect1.end(), back_inserter(vect2));

    cout << "Old vector elements are : ";
    for (int i=0; i<vect1.size(); i++)
        cout << vect1[i] << " ";
    cout << endl;

    cout << "New vector elements are : ";
    for (int i=0; i<vect2.size(); i++)
        cout << vect2[i] << " ";
    cout<< endl;

    // Changing value of vector to show that a new
    // copy is created.
    vect1[0] = 2;

    cout << "The first element of old vector is :";
    cout << vect1[0] << endl;
    cout << "The first element of new vector is :";
    cout << vect2[0] <<endl;

    return 0;
}
```

输出：

```cpp
Old vector elements are : 1 2 3 4 
New vector elements are : 1 2 3 4 
The first element of old vector is :2
The first element of new vector is :1
```

*   **`assign(first_iterator_o, last_iterator_o)`**：此方法将与旧向量相同的值赋给新向量。它接受 2 个参数，第一个是旧向量的起始迭代器，第二个是旧向量的结束迭代器。这会生成一个深拷贝。

```cpp
// C++ code to demonstrate copy of vector
// by assign()
#include<iostream>
#include<vector> // for vector
#include<algorithm> // for copy() and assign()
#include<iterator> // for back_inserter
using namespace std;

int main()
{
    // Initializing vector with values
    vector<int> vect1{1, 2, 3, 4};

    // Declaring another vector
    vector<int> vect2;

    // Copying vector by assign function
    vect2.assign(vect1.begin(), vect1.end());

    cout << "Old vector elements are : ";
    for (int i=0; i<vect1.size(); i++)
        cout << vect1[i] << " ";
    cout << endl;

    cout << "New vector elements are : ";
    for (int i=0; i<vect2.size(); i++)
        cout << vect2[i] << " ";
    cout<< endl;

    // Changing value of vector to show that a new
    // copy is created.
    vect1[0] = 2;

    cout << "The first element of old vector is :";
    cout << vect1[0] << endl;
    cout << "The first element of new vector is :";
    cout << vect2[0] <<endl;

    return 0;
}
```

输出：

```cpp
Old vector elements are : 1 2 3 4 
New vector elements are : 1 2 3 4 
The first element of old vector is :2
The first element of new vector is :1
```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。