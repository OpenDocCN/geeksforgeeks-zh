# STD::c++ 中的 valarray 类

> 原文:[https://www.geeksforgeeks.org/std-valarray-class-c/](https://www.geeksforgeeks.org/std-valarray-class-c/)

C++ 98 引入了一个名为 valarray 的特殊容器，可以有效地保存和提供数组上的数学运算。

*   Support element mathematical operations and various forms of generalized subscript operators, slicing and indirect access.
*   Compared with vectors, arrays are also more effective than vectors in some mathematical operations.

**valarray 类中的公共成员函数:**

**1。apply()** :-该函数**将其参数**中给出的操作**一次应用于所有的**valarray 元素，**返回一个带有操作值的新 valarray** 。

**2。sum()** :-这个函数**一次返回 valarrays 所有元素的总和**。

```cpp
// C++ code to demonstrate the working of 
// apply() and sum()
#include<iostream>
#include<valarray> // for valarray functions
using namespace std;
int main()
{
    // Initializing valarray
    valarray<int> varr = { 10, 2, 20, 1, 30 };

    // Declaring new valarray
    valarray<int> varr1 ;

    // Using apply() to increment all elements by 5
    varr1 = varr.apply([](int x){return x=x+5;});

    // Displaying new elements value
    cout << "The new valarray with manipulated values is : ";
    for (int &x: varr1) cout << x << " ";
    cout << endl;

    // Displaying sum of both old and new valarray
    cout << "The sum of old valarray is : ";
    cout << varr.sum() << endl;
    cout << "The sum of new valarray is : ";
    cout << varr1.sum() << endl;

    return 0;

}
```

输出:

```cpp
The new valarray with manipulated values is : 15 7 25 6 35 
The sum of old valarray is : 63
The sum of new valarray is : 88

```

**3。min()** :-该函数返回 valarray 的**最小的**元素。

**4。max()** :-该函数返回 valarray 中最大的**元素。**

```cpp
// C++ code to demonstrate the working of 
// max() and min()
#include<iostream>
#include<valarray> // for valarray functions
using namespace std;
int main()
{
    // Initializing valarray
    valarray<int> varr = { 10, 2, 20, 1, 30 };

    // Displaying largest element of valarray
    cout << "The largest element of valarray is : ";
    cout << varr.max() << endl;

    // Displaying smallest element of valarray
    cout << "The smallest element of valarray is : ";
    cout << varr.min() << endl;

    return 0;

}
```

**输出:**

```cpp
The largest element of valarray is : 30
The smallest element of valarray is : 1 
```

****5。shift()** :-该函数通过参数中提到的号**返回**移动元素** **后的新 valarray。如果**号为正**，**左移**，如果**号为负**，则**右移**。******

**6。cs shift()**:-该函数通过参数中提到的号**循环移位(旋转)**元素**后返回新的 valarray。如果**号为正，则应用左循环** **换档**，如果**号为负，则应用右循环换档**。**

```cpp
// C++ code to demonstrate the working of 
// shift() and cshift()
#include<iostream>
#include<valarray> // for valarray functions
using namespace std;
int main()
{
    // Initializing valarray
    valarray<int> varr = { 10, 2, 20, 1, 30 };

    // Declaring new valarray
    valarray<int> varr1;

    // using shift() to shift elements to left
    // shifts valarray by 2 position
    varr1 = varr.shift(2);

    // Displaying elements of valarray after shifting
    cout << "The new valarray after shifting is : ";
    for ( int&x : varr1) cout << x << " ";
    cout << endl;

    // using cshift() to circulary shift elements to right
    // rotates valarray by 3 position
    varr1 = varr.cshift(-3);

    // Displaying elements of valarray after circular shifting
    cout << "The new valarray after circular shifting is : ";
    for ( int&x : varr1) cout << x << " ";
    cout << endl;

    return 0;

}
```

输出:

```cpp
The new valarray after shifting is : 20 1 30 0 0 
The new valarray after circular shifting is : 20 1 30 10 2 

```

**7。swap()** :-此功能**将一个 valarray 与另一个 valarray 互换**。

```cpp
// C++ code to demonstrate the working of 
// swap()
#include<iostream>
#include<valarray> // for valarray functions
using namespace std;
int main()
{
   // Initializing 1st valarray
    valarray<int> varr1 = {1, 2, 3, 4};

    // Initializing 2nd valarray
    valarray<int> varr2 = {2, 4, 6, 8};

     // Displaying valarrays before swapping
     cout << "The contents of 1st valarray "
             "before swapping are : ";
     for (int &x : varr1)
         cout << x << " ";
     cout << endl;
     cout << "The contents of 2nd valarray "
             "before swapping are : ";
     for (int &x : varr2)
         cout << x << " ";
     cout << endl;

     // Use of swap() to swap the valarrays
     varr1.swap(varr2);

     // Displaying valarrays after swapping
     cout << "The contents of 1st valarray "
             "after swapping are : ";
     for (int &x : varr1)
         cout << x << " ";
     cout << endl;

     cout << "The contents of 2nd valarray "
             "after swapping are : ";
     for (int &x : varr2)
         cout << x << " ";
     cout << endl;

    return 0;

}
```

输出:

```cpp
The contents of 1st valarray before swapping are : 1 2 3 4 
The contents of 2nd valarray before swapping are : 2 4 6 8 
The contents of 1st valarray after swapping are : 2 4 6 8 
The contents of 2nd valarray after swapping are : 1 2 3 4 

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。