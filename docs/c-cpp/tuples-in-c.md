# c++ 中的元组

> 原文:[https://www.geeksforgeeks.org/tuples-in-c/](https://www.geeksforgeeks.org/tuples-in-c/)

**什么是元组？**
元组是可以容纳多个元素的对象。元素可以是不同的数据类型。元组的元素按照被访问的顺序被初始化为参数。

**元组**上的操作:-

**1。get()** :- get()用于访问元组值并修改它们，它接受索引和元组名称作为参数来访问特定的元组元素。

**2。make_tuple()** :- make_tuple()用于给 tuple 赋值。传递的值应该与元组中声明的值保持一致。

```cpp
// C++ code to demonstrate tuple, get() and make_pair()
#include<iostream>
#include<tuple> // for tuple
using namespace std;
int main()
{
    // Declaring tuple
    tuple <char, int, float> geek;

    // Assigning values to tuple using make_tuple()
    geek = make_tuple('a', 10, 15.5);

    // Printing initial tuple values using get()
    cout << "The initial values of tuple are : ";
    cout << get<0>(geek) << " " << get<1>(geek);
    cout << " " << get<2>(geek) << endl;

    // Use of get() to change values of tuple
    get<0>(geek) = 'b';
    get<2>(geek) =  20.5;

     // Printing modified tuple values
    cout << "The modified values of tuple are : ";
    cout << get<0>(geek) << " " << get<1>(geek);
    cout << " " << get<2>(geek) << endl;

    return 0;
}
```

输出:

```cpp
The initial values of tuple are : a 10 15.5
The modified values of tuple are : b 10 20.5

```

在上面的代码中，get()修改了元组的第 1 和第 3 个值。

**3。tuple_size** :-返回元组中存在的元素数量。

```cpp
//C++ code to demonstrate tuple_size
#include<iostream>
#include<tuple> // for tuple_size and tuple
using namespace std;
int main()
{

    // Initializing tuple
    tuple <char,int,float> geek(20,'g',17.5);

    // Use of size to find tuple_size of tuple
    cout << "The size of tuple is : ";
    cout << tuple_size<decltype(geek)>::value << endl;

    return 0;

}
```

输出:

```cpp
The size of tuple is : 3

```

**4。swap()**:-swap()，交换两个不同元组的元素。

```cpp
//C++ code to demonstrate swap()
#include<iostream>
#include<tuple> // for swap() and tuple
using namespace std;
int main()
{

    // Initializing 1st tuple
    tuple <int,char,float> tup1(20,'g',17.5);

    // Initializing 2nd tuple
    tuple <int,char,float> tup2(10,'f',15.5);

    // Printing 1st and 2nd tuple before swapping
    cout << "The first tuple elements before swapping are : ";
    cout <<  get<0>(tup1) << " " << get<1>(tup1) << " "
         << get<2>(tup1) << endl;
    cout << "The second tuple elements before swapping are : ";
    cout <<  get<0>(tup2) << " " << get<1>(tup2) << " " 
         << get<2>(tup2) << endl;

    // Swapping tup1 values with tup2
    tup1.swap(tup2);

    // Printing 1st and 2nd tuple after swapping
    cout << "The first tuple elements after swapping are : ";
    cout <<  get<0>(tup1) << " " << get<1>(tup1) << " " 
         << get<2>(tup1) << endl;
    cout << "The second tuple elements after swapping are : ";
    cout <<  get<0>(tup2) << " " << get<1>(tup2) << " " 
         << get<2>(tup2) << endl;

    return 0;
}
```

输出:

```cpp
The first tuple elements before swapping are : 20 g 17.5
The second tuple elements before swapping are : 10 f 15.5
The first tuple elements after swapping are : 10 f 15.5
The second tuple elements after swapping are : 20 g 17.5

```

**5。tie()**:-tie()的工作是将元组值解包到单独的变量中。tie()有两种变体，有“忽略”和没有“忽略”，其中“忽略”会忽略特定的元组元素，并阻止它被解包。

```cpp
// C++ code to demonstrate working of tie()
#include<iostream>
#include<tuple> // for tie() and tuple
using namespace std;
int main()
{   
    // Initializing variables for unpacking
    int i_val;
    char ch_val;
    float f_val;   

    // Initializing tuple
    tuple <int,char,float> tup1(20,'g',17.5);

    // Use of tie() without ignore
    tie(i_val,ch_val,f_val) = tup1;

    // Displaying unpacked tuple elements
    // without ignore
    cout << "The unpacked tuple values (without ignore) are : ";
    cout << i_val << " " << ch_val << " " << f_val;
    cout << endl;

    // Use of tie() with ignore
    // ignores char value
    tie(i_val,ignore,f_val) = tup1;

    // Displaying unpacked tuple elements
    // with ignore
    cout << "The unpacked tuple values (with ignore) are : ";
    cout << i_val  << " " << f_val;
    cout << endl;

    return 0;

}
```

输出:

```cpp
The unpacked tuple values (without ignore) are : 20 g 17.5
The unpacked tuple values (with ignore) are : 20 17.5

```

**6。tuple_cat()** :-这个函数连接两个元组，并返回一个新的元组。

```cpp
// C++ code to demonstrate working of tuple_cat()
#include<iostream>
#include<tuple> // for tuple_cat() and tuple
using namespace std;
int main()
{
    // Initializing 1st tuple
    tuple <int,char,float> tup1(20,'g',17.5);

    // Initializing 2nd tuple
    tuple <int,char,float> tup2(30,'f',10.5);

    // Concatenating 2 tuples to return a new tuple
    auto tup3 = tuple_cat(tup1,tup2);

    // Displaying new tuple elements
    cout << "The new tuple elements in order are : ";
    cout << get<0>(tup3) << " " << get<1>(tup3) << " ";
    cout << get<2>(tup3) << " " << get<3>(tup3) << " ";
    cout << get<4>(tup3) << " " << get<5>(tup3) << endl;

    return 0;
}
```

输出:

```cpp
The new tuple elements in order are : 20 g 17.5 30 f 10.5

```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。