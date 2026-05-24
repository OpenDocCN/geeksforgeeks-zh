# c++ STL 中的数值头|集合 2(相邻 _ 差()、内积()和 iota())

> 原文:[https://www . geeksforgeeks . org/numeric-header-in-c-STL-set-2-相邻 _ difference-inner _ product-and-iota/](https://www.geeksforgeeks.org/numeric-header-in-c-stl-set-2-adjacent_difference-inner_product-and-iota/)

 [c++ STL 中的数字表头|集合 1](https://www.geeksforgeeks.org/numeric-header-in-c-stl-set-1-accumulate-and-partial_sum/)

**相邻 _ 差异**

这个函数将一个数组的对应元素之间的差异分配给另一个数组。它返回位于【第一个，最后一个】之间的所有值集的**相邻差值。**

例如:如果 a[]代表提供的范围[第一个，最后一个]中的元素，b[]代表结果。

```cpp
b[0] = a[1] 
b[1] = a[1] – a[0] 
b[2] = a[2] – a[1] 
b[3] = a[3] – a[2] 
b[4] = a[4] – a[3] 
... ... ...

```

**语法:**

```cpp
adjacent_difference(first, last, b);
adjacent_difference(first, last, b, myfun );
adjacent_difference(first, last, b, multiplies() ) ;

first, last : address of first and last element of range whose elements are to be added
b:index of array where  corresponding partial sum will be stored;
myfun : a user defined function for performing any specific task
multiplies():a pre defined function.

```

```cpp
#include <iostream> 
#include <functional> // for multiplies function
#include <numeric>   //for adjacent_difference

using namespace std;

int myfun (int x, int y) 
{
    return x+y;
}

int main () 
{
    int a[] = { 1, 2, 3, 4, 5, 6} ;
    int b[6];

    // using adjacent_difference function
    adjacent_difference (a, a+6, b);
    cout << "\nResult using adjacent_difference: ";
    for (int i=0; i<6; i++) 
        std::cout << b[i] << ' ' ;   

    // using adjacent_difference function
    // user defined function    
    adjacent_difference (a, a+6, b, myfun);
    cout << "\nResult using accumulate with user-"
             "defined function: ";
    for (int i=0; i<6; i++) 
        std::cout << b[i] << ' ';

    // using adjacent_difference with pre-defined function
    adjacent_difference (a, a+6, b, multiplies<int>() ) ;

    cout << "\nResult using accumulate with pre-defined function: " ;
    for (int i=0; i<6; i++) 
        std::cout << b[i] << ' ';

    return 0;
}
```

**输出:**

```cpp
Result using adjacent_difference: 1 1 1 1 1 1 
Result using accumulate with user-defined function: 1 3 5 7 9 11 
Result using accumulate with pre-defined function: 1 2 6 12 20 30 

```

**内积**

这个函数返回 var 与从第一个 1 和第一个 2 开始的两个范围的元素形成的对的内积相加的结果。

**语法:**

```cpp
inner_product(first, last, b, var) ;
inner_product(a, a+3, b, var, fun, fun1) ;
inner_product(a , a+3, b, init, minus (), divides () );

first, last : address of first and last element of range whose elements are to be added
b: index of array where  corresponding partial sum will be stored;
fun, fun1: a user defined function for performing any specific task
minus(), divides()  : pre defined function.

```

```cpp
#include <iostream>  
#include <functional> // for subtraction, std::divides
#include <numeric>   // for inner_product

using namespace std;

int fun (int x, int y) 
{
    return x-y;
}

int fun1 (int x, int y) 
{
    return x+y;
}

int main () 
{
    int var = 200;
    int a[] = { 10, 15, 20} ;
    int b[] = { 1, 3, 5} ;

    cout << "\nResult using inner_product " ;    

    // inner_product with default method
    cout << inner_product(a, a+3, b, var ) ;

    // inner_product with pre-defined function
    cout << "\nResult using inner_product with pre-defined function: ";
    cout << inner_product(a, a+3, b, var, minus<int>(), divides<int>());

    // inner_product with user defined function
    cout << "\nResult using inner_product with user-defined function: ";
    cout << inner_product(a, a+3, b, var, fun, fun1);

    return 0;
}
```

**输出:**

```cpp
Result using inner_product 355
Result using inner_product with pre-defined function: 181
Result using inner_product with user-defined function: 146

```

**iota**

该函数为数组范围[第一个，最后一个]中的元素赋值，该值在每一步递增 val++。

**语法–**

```cpp
iota(first, last,val) ;

first, last : address of first and last element of range whose elements are to be added
val: initial value to store, the expression ++ value must be well-formed

```

```cpp
#include <iostream> 
#include <iostream> 
#include <numeric>   // std::iota
using namespace std;

int main ( )
{
    int a[7];

    //using iota function to store 100, 101, 102,...    
    iota(a, a+7,100);
    cout << " a : " ;
    for (int& x: a) 
        cout << ' ' << x;

    return 0;
}
```

**输出:**

```cpp
a: 100 101 102 103 104 105 106 

```

本文由 **[阿比纳夫·蒂瓦里](https://auth.geeksforgeeks.org/profile.php?user=Abhinav%20Tiwari&list=todoDone)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。