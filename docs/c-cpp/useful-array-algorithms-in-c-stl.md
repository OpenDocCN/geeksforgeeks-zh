# c++ STL 中的数组算法(all_of、any_of、none_of、copy_n 和 iota)

> 原文:[https://www . geesforgeks . org/有用-数组-算法-in-c-stl/](https://www.geeksforgeeks.org/useful-array-algorithms-in-c-stl/)

从 C++ 11 开始，在 C++ 的 STL 中加入了一些新的有趣的算法。这些算法在数组上运行，有助于节省编码时间，因此在竞争性编程中也很有用。

**all_of()**

该函数对整个数组元素范围进行操作，并且可以节省时间来运行循环来逐个检查每个元素。它检查每个元素的给定属性，当范围内的每个元素满足指定属性时返回 true，否则返回 false。

```cpp
// C++ code to demonstrate working of all_of()
#include<iostream>
#include<algorithm> // for all_of()
using namespace std;
int main()
{
    // Initializing array
    int ar[6] =  {1, 2, 3, 4, 5, -6};

    // Checking if all elements are positive
    all_of(ar, ar+6, [](int x) { return x>0; })?
          cout << "All are positive elements" :
          cout << "All are not positive elements";

    return 0;

}
```

输出:

```cpp
All are not positive elements

```

在上面的代码中，-6 是一个否定的元素，否定了这个条件并返回 false。

**任意 _of()**

这个函数检查给定的范围，如果有一个元素满足函数中提到的给定属性。如果至少有一个元素满足属性，则返回 true，否则返回 false。

```cpp
// C++ code to demonstrate working of any_of()
#include<iostream>
#include<algorithm> // for any_of()
using namespace std;
int main()
{
    // Initializing array
    int ar[6] =  {1, 2, 3, 4, 5, -6};

    // Checking if any element is negative
    any_of(ar, ar+6, [](int x){ return x<0; })?
          cout << "There exists a negative element" :
          cout << "All are positive elements";

    return 0;

}
```

输出:

```cpp
There exists a negative element

```

在上面的代码中，-6 使条件为正。

**none_of()**

如果没有任何元素满足给定条件，则此函数返回 true，否则返回 false。

```cpp
// C++ code to demonstrate working of none_of()
#include<iostream>
#include<algorithm> // for none_of()
using namespace std;
int main()
{
    // Initializing array
    int ar[6] =  {1, 2, 3, 4, 5, 6};

    // Checking if no element is negative
    none_of(ar, ar+6, [](int x){ return x<0; })?
          cout << "No negative elements" :
          cout << "There are negative elements";

    return 0;
}
```

输出:

```cpp
No negative elements

```

因为所有元素都是正的，所以函数返回真。

**copy_n()**

copy_n()将一个数组元素复制到新数组。这种类型的拷贝会创建阵列的深度拷贝。这个函数接受 3 个参数，源数组名，数组大小和目标数组名。

```cpp
// C++ code to demonstrate working of copy_n()
#include<iostream>
#include<algorithm> // for copy_n()
using namespace std;
int main()
{
    // Initializing array
    int ar[6] =  {1, 2, 3, 4, 5, 6};

    // Declaring second array
    int ar1[6];

    // Using copy_n() to copy contents
    copy_n(ar, 6, ar1);

    // Displaying the copied array
    cout << "The new array after copying is : ";
    for (int i=0; i<6 ; i++)
       cout << ar1[i] << " ";

    return 0;

}
```

输出:

```cpp
The new array after copying is : 1 2 3 4 5 6

```

在上面的代码中，使用 copy_n()
在 ar1 中复制 ar 的元素

**iota()**

此函数用于将连续值赋给数组。这个函数接受 3 个参数，数组名、大小和起始数字。

```cpp
// C++ code to demonstrate working of iota()
#include<iostream>
#include<numeric> // for iota()
using namespace std;
int main()
{
    // Initializing array with 0 values
    int ar[6] =  {0};

    // Using iota() to assign values
    iota(ar, ar+6, 20);

    // Displaying the new array
    cout << "The new array after assigning values is : ";
    for (int i=0; i<6 ; i++)
       cout << ar[i] << " ";

    return 0;

}
```

输出:

```cpp
The new array after assigning values is : 20 21 22 23 24 25

```

在上面的代码中，使用 iota()将连续值分配给数组。

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。