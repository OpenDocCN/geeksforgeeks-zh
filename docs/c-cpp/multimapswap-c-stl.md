# c++ STL 中的 multimap::swap()

> 原文:[https://www.geeksforgeeks.org/multimapswap-c-stl/](https://www.geeksforgeeks.org/multimapswap-c-stl/)

multimap::swap()用于将一个 multimap 的内容与另一个相同类型和大小的 multimap 进行交换。

语法:-

```cpp
multimap1.swap(multimap2)

```

**参数:**
必须与之交换内容的多重映射的名称。
**结果:**
2 个多地图的所有元素都被交换了。

示例:

```cpp
Input:   multimap1 = { ('a',1), ('b',2), ('c',3)
         multimap2 = ( ('d',4), ('e',5) )
         multimap1.swap(multimap2);

Output:  MultiMap 1 data
         ('d', 4), ('e', 5) 

         MultiMap 2 data
         ('a',1), ('b',2), ('c',3)

Input:  multimap1 = { ('abc',10) , ('bef',12) , ('efg',13)
        multimap2 = ( ('def',14), ('ehi',15) )
        multimap1.swap(multimap2);

Output: multimap 1 data
        ('def',14), ('ehi',15)

        multimap 2 data
        ('abc',10) , ('bef',12) , ('efg',13)

```

```cpp
// CPP Program to illustrate...
#include<iostream>
#include<map>
using namespace std;

int main()
{
    // initialize multimap
    multimap<char,int > m1;
    multimap<char,int> m2;

    // iterator for iterate all 
    // element of multimap
    multimap<char,int >:: iterator iter;

    // multimap1 data
    m1.insert(make_pair('a',1));
    m1.insert(make_pair('b',2));
    m1.insert(make_pair('c',3));

    // multimap2 data
    m2.insert(make_pair('d',4));
    m2.insert(make_pair('e',5));

    // swap multimap1 data with
    // multimap2 data
    m1.swap(m2);

    // multimap1 data
    cout << "MultiMap 1 data" << "\n";
    for( iter = m1.begin() ;
         iter != m1.end() ; iter++)

    cout << (*iter).first << " " 
         << (*iter).second << "\n";

    // multimap2 data
    cout << "MultiMap 2 data" << "\n";
    for( iter = m2.begin() ;
         iter != m2.end() ; iter++ )

    cout << (*iter).first << " " 
         << (*iter).second << "\n";
}
```

输出:-

```cpp
MultiMap 1 data
d 4
e 5
MultiMap 2 data
a 1
b 2
c 3

```