# c++ 中的 sort_heap 函数

> 原文:[https://www.geeksforgeeks.org/sort_heap-function-in-c/](https://www.geeksforgeeks.org/sort_heap-function-in-c/)

**sort_heap( )** 是一种 STL 算法，在开始和结束指定的范围内对堆进行排序。将堆范围[开始，结束]中的元素按升序排序。

第二种形式允许您指定一个比较函数来确定一个元素何时小于另一个元素。
在表头**定义**

****有两个版本，定义如下:**。
T3】1。使用“<”比较元素:
语法:**

```cpp
template 
**void sort_heap(RandIter start, RandIter end);**
**start, end : **    the range of elements to sort
**Return Value:**  Since, return type is void, so it doesnot return any value. 
```

****实施****

```cpp
template
void sort_heap( RandIter start, RandIter end );
{
    while (start != end)
        std::pop_heap(start, end--);
} 
```

****2。通过使用预定义函数进行比较:**
**语法:****

```cpp
**template 
void sort_heap(RandIter start, RandIter end, Comp cmpfn);**
**start, end :**    the range of elements to sort
**comp:**   comparison function object (i.e. an object that satisfies the requirements of Compare) 
which returns ?true if the first argument is less than the second.
**Return Value :** Since, its return type is void, so it doesnot return any value. 
```

****实施****

```cpp
template
void sort_heap( RandIter start, RandIter end, Comp cmpfn );
{
    while (start != end)
        std::pop_heap(start, end--, cmpfn);
} 
```

```cpp
// CPP program to illustrate
// std::sort_heap
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main()
{
    vector<int> v = {8, 6, 2, 1, 5, 10}; 

    make_heap(v.begin(), v.end());

    cout << "heap:   ";
    for (const auto &i : v) {
     cout << i << ' ';
    }   

    sort_heap(v.begin(), v.end());

    std::cout <<endl<< "now sorted:   ";
    for (const auto &i : v) {                                                   
        cout << i << ' ';
    }   
    std::cout <<endl;
}
```

**输出:**

```cpp
heap: 10 6 8 1 5 2 
now sorted: 1 2 5 6 8 10 
```

****另一个例子:****

```cpp
// CPP program to illustrate
// std::sort_heap
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main( ) {
   using namespace std;
   vector <int> vt1, vt2;
   vector <int>::iterator Itera1, Itera2;

   int i;
   for ( i = 1 ; i <=5 ; i++ )
      vt1.push_back( i );

   random_shuffle( vt1.begin( ), vt1.end( ) );

   cout << "vector vt1 is ( " ;
   for ( Itera1 = vt1.begin( ) ; Itera1 != vt1.end( ) ; Itera1++ )
      cout << *Itera1 << " ";
   cout << ")" << endl;

   sort_heap (vt1.begin( ), vt1.end( ) );
   cout << "heap vt1 sorted range: ( " ;
   for ( Itera1 = vt1.begin( ) ; Itera1 != vt1.end( ) ; Itera1++ )
      cout << *Itera1 << " ";
   cout << ")" << endl;
}

```

**输出:**

```cpp
vector vt1 is ( 5 4 2 3 1 )
heap vt1 sorted range: ( 1 2 3 4 5 ) 
```

**本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**