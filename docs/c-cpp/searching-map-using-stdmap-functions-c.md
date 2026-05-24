# 使用 C++ 中的 std::map 函数在地图中搜索

> 原文:[https://www . geesforgeks . org/search-map-use-stdmap-functions-c/](https://www.geeksforgeeks.org/searching-map-using-stdmap-functions-c/)

通常，使用[地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/) stl 容器的主要目的是为了**高效的搜索操作和排序顺序检索**。由于地图存储键值对，所有搜索操作都需要“ **O(log(n))** ”时间(n 是地图的大小)。C++ 语言中存在不同类型的搜索函数，每种函数都有不同的功能。在竞争性编程的环境中，当需要搜索操作并且性能优于其他容器时，这将非常有用。下面讨论一些搜索操作。

**std::map::find()**

find()用于**搜索键值**对，并接受其参数中的“key”进行查找。如果找到该元素，该函数返回指向该元素的指针，否则返回指向地图最后位置的指针，即“ **map.end()** ”。

```cpp
// C++ code to demonstrate the working of find()

#include<iostream>
#include<map> // for map operations
using namespace std;

int main()
{
    // declaring map
    // of char and int
    map< char, int > mp;

    // declaring iterators
    map<char, int>::iterator it ;
    map<char, int>::iterator it1 ;

    // inserting values 
    mp['a']=5;
    mp['b']=10;
    mp['c']=15;
    mp['d']=20;
    mp['e']=30;

    // using find() to search for 'b' 
    // key found
    // "it" has address of key value pair.
    it = mp.find('b');

    if(it == mp.end())
        cout << "Key-value pair not present in map" ;
    else
        cout << "Key-value pair present : " 
          << it->first << "->" << it->second ;

    cout << endl ;

    // using find() to search for 'm' 
    // key not found
    // "it1" has address of end of map.
    it1 = mp.find('m');

    if(it1 == mp.end())
        cout << "Key-value pair not present in map" ;
    else
        cout << "Key-value pair present : " 
            << it1->first << "->" << it1->second ;

}
```

输出:

```cpp
Key-value pair present : b->10
Key-value pair not present in map

```

**std::map::下界()**

lower_bound()也用于搜索操作，但有时也会返回有效的键值对，即使它不在 map 中。lower_bound()返回键值对的**地址，如果映射中有一个，则返回大于其参数中提到的键的最小键的地址。如果所有键都比要找到的键小，则指向“map . end()”**。

```cpp
// C++ code to demonstrate the working of lower_bound()

#include<iostream>
#include<map> // for map operations
using namespace std;

int main()
{
    // declaring map
    // of char and int
    map< char, int > mp;

    // declaring iterators
    map<char, int>::iterator it ;
    map<char, int>::iterator it1 ;
    map<char, int>::iterator it2 ;

    // inserting values 
    mp['a']=5;
    mp['b']=10;
    mp['c']=15;
    mp['h']=20;
    mp['k']=30;

    // using lower_bound() to search for 'b' 
    // key found
    // "it" has address of key value pair.
    it = mp.lower_bound('b');

    if(it == mp.end())
        cout << "Key-value pair not present in map" ;
    else
        cout << "Key-value pair returned : " 
            << it->first << "->" << it->second ;

    cout << endl ;

    // using lower_bound() to search for 'd' 
    // key not found
    // "it1" has address of next greater key.
    // key - 'h'
    it1 = mp.lower_bound('d');

    if(it1 == mp.end())
        cout << "Key-value pair not present in map" ;
    else
        cout << "Key-value pair returned : " 
            << it1->first << "->" << it1->second ;

    cout << endl;

    // using lower_bound() to search for 'p' 
    // key not found
    // "it2" has address of next greater key.
    // all keys are smaller, hence returns mp.end()
    it2 = mp.lower_bound('p');

    if(it2 == mp.end())
        cout << "Key-value pair not present in map" ;
    else
        cout << "Key-value pair returned : "
            << it2->first << "->" << it2->second ;

}
```

输出:

```cpp
Key-value pair returned : b->10
Key-value pair returned : h->20
Key-value pair not present in map

```

**std::map::upper_bound()**

upper_bound()也用于搜索操作，**从不返回在**中搜索的键值对。upper_bound()返回**键值对的**地址，如果在地图中存在的话，该地址正好位于搜索到的关键字的下一个**处。如果所有键都小于要查找的键，则指向“map . end()”**

```cpp
// C++ code to demonstrate the working of upper_bound()

#include<iostream>
#include<map> // for map operations
using namespace std;

int main()
{
    // declaring map
    // of char and int
    map< char, int > mp;

    // declaring iterators
    map<char, int>::iterator it ;
    map<char, int>::iterator it1 ;
    map<char, int>::iterator it2 ;

    // inserting values 
    mp['a']=5;
    mp['b']=10;
    mp['c']=15;
    mp['h']=20;
    mp['k']=30;

    // using upper_bound() to search for 'b' 
    // key found
    // "it" has address of key value pair next to 'b' i.e 'c'.
    it = mp.upper_bound('b');

    if(it == mp.end())
        cout << "Key-value pair not present in map" ;
    else
        cout << "Key-value pair returned : " 
            << it->first << "->" << it->second ;

    cout << endl ;

    // using upper_bound() to search for 'd' 
    // key not found
    // "it1" has address of next greater key.
    // key - 'h'
    it1 = mp.upper_bound('d');

    if(it1 == mp.end())
        cout << "Key-value pair not present in map" ;
    else
        cout << "Key-value pair returned : " 
        << it1->first << "->" << it1->second ;

    cout << endl;

    // using upper_bound() to search for 'p' 
    // key not found
    // "it2" has address of next greater key.
    // all keys are smaller, hence returns mp.end()
    it2 = mp.upper_bound('p');

    if(it2 == mp.end())
        cout << "Key-value pair not present in map" ;
    else
        cout << "Key-value pair returned : " 
            << it2->first << "->" << it2->second ;

}
```

输出:

```cpp
Key-value pair returned : c->15
Key-value pair returned : h->20
Key-value pair not present in map

```

**标准::地图::等距离**

还有一个在地图中搜索的功能，它**返回包含搜索关键字**的范围。由于映射包含唯一元素，返回范围最多包含 1 个元素。此函数**返回一个对的迭代器，其第一个元素指向搜索到的键对的下界()，第二个元素指向搜索到的键的上界()。如果键不存在，则第一个元素和第二个元素都指向下一个更大的元素。**

```cpp
// C++ code to demonstrate the working of equal_range()

#include<iostream>
#include<map> // for map operations
using namespace std;

int main()
{
    // declaring map
    // of char and int
    map< char, int > mp;

    // declaring iterators
    pair<map<char, int>::iterator, map<char, int>::iterator> it;

    // inserting values 
    mp['a']=5;
    mp['b']=10;
    mp['c']=15;
    mp['h']=20;
    mp['k']=30;

    // using equal_range() to search for 'b' 
    // key found
    // 1st element of "it" has the address to lower_bound (b)
    // 2nd element of "it" has the address to upper_bound (c) 
    it = mp.equal_range('b');

    cout << "The lower_bound of key is : " 
        << it.first -> first << "->" << it.first -> second;
    cout << endl;

    cout << "The upper_bound of key is : " 
        << it.second -> first << "->" << it.second -> second;

    cout << endl << endl ;

    // using equal_range() to search for 'd' 
    // key not found
    // Both elements of it point to next greater key
    // key - 'h'
    it = mp.equal_range('d');

    cout << "The lower_bound of key is : " 
        << it.first -> first << "->" << it.first -> second;
    cout << endl;

    cout << "The upper_bound of key is : " 
        << it.second -> first << "->" << it.second -> second;

}
```

输出:

```cpp
The lower_bound of key is : b->10
The upper_bound of key is : c->15

The lower_bound of key is : h->20
The upper_bound of key is : h->20

```

本文由 **[【曼吉特·辛格】](https://www.facebook.com/manjeet.04.singh)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。