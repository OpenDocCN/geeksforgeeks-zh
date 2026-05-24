# C++ 中的 `lexicographical_compare()`

> 原文: [https://www.geeksforgeeks.org/lexicographical_compare-in-cpp-2/](https://www.geeksforgeeks.org/lexicographical_compare-in-cpp-2/)

C++ STL 提供了许多实用程序来解决基本的常见生活问题。比较值总是必要的，但有时我们也需要比较字符串。因此，本文旨在解释关于 `lexicographical_compare()`，它允许比较字符串。该功能在 `<algorithm>` 头文件中定义。它有两个实现。

## 实现 1: `lexicographical_compare(iter1 beg1, iter1 end1, iter2 beg2, iter2 end2)`

```cpp
Template:
template <class iter1, class iter2>
  bool lexicographical_compare(iter1 beg1, iter1 end1, 
                               iter2 beg2, iter2 end2)
{
  while (beg1!=end1)
  {
    if (beg2==end2 || *beg2<*beg1) return false;
    else if (*beg1<*beg2) return true;
    ++ beg1; ++ beg2;
  }
  return (beg2!=end2);
}
Parameters : 
beg1 :  Input iterator to initial position of first sequence.
end1 :  Input iterator to final position of first sequence.

beg2 :  Input iterator to initial position of second sequence.
end2 :  Input iterator to final position of second sequence.

Return value : 
Returns a boolean true, if range1 is strictly lexicographically 
smaller than range2 else returns a false.
```

```cpp
// C++ code to demonstrate the working of
// lexicographical_compare(), implementation 1
#include <iostream>
#include <algorithm> // for lexicographical_compare()
using namespace std;

int main()
{
    // initializing char arrays
    char one[] = "geeksforgeeks";
    char two[] = "gfg";

    // using lexicographical_compare for checking
    // is "one" is less than "two"
    if (lexicographical_compare(one, one + 13, two, two + 3)) 
        cout << "geeksforgeeks is lexicographically less "
                                        "than gfg";
    else 
        cout << "geeksforgeeks is not lexicographically "
                                        "less than gfg";    
}
```

输出:

```
geeksforgeeks is lexicographically less than gfg
```

## 实现 2: `lexicographical_compare(iter1 beg1, iter1 end1, iter2 beg2, iter2 end2, Compare comp)`

```cpp
Template:
template <class iter1, class iter2, class Compare>
  bool lexicographical_compare(iter1 beg1, iter1 end1, 
                               iter2 beg2, iter2 end2, Compare comp)
{
  while (beg1!=end1)
  {
    if (beg2==end2 || comp(*beg2, *beg1)) return false;
    else if (comp(*beg1, *beg2)) return true;
    ++ beg1; ++ beg2;
  }
  return (beg2!=end2);
}
Parameters : 
beg1 :  Input iterator to initial position of first sequence.
end1 :  Input iterator to final position of first sequence.

beg2 :  Input iterator to initial position of second sequence.
end2 :  Input iterator to final position of second sequence.

comp : The comparator function that returns a boolean
true/false of the each elements compared. This function 
accepts two arguments. This can be function pointer or 
function object and cannot change values.

Return value : 
Returns a boolean true, if range1 is strictly lexicographically smaller 
than range2 else returns a false.
```

```cpp
// C++ code to demonstrate the working of
// lexicographical_compare(), implementation 2

#include <iostream>
#include <algorithm> // for lexicographical_compare()
using namespace std;

// helper function to convert all into lower case:
bool comp(char s1, char s2)
{
    return tolower(s1) < tolower(s2);
}

int main()
{
    // initializing char arrays
    char one[] = "geeksforgeeks";
    char two[] = "Gfg";

    // using lexicographical_compare for checking
    // is "one" is less than "two"
    // returns false as "g" has larger ASCII value than "G"
    if (lexicographical_compare(one, one + 13, two, two + 3)) 
        cout << "geeksforgeeks is lexicographically less "
                                "than Gfg\n";
    else 
        cout << "geeksforgeeks is not lexicographically "
                                "less than Gfg\n";

    // using lexicographical_compare for checking
    // is "one" is less than "two"
    // returns true this time as all converted into lowercase
    if (lexicographical_compare(one, one + 13, two, two + 3, comp)) {
        cout << "geeksforgeeks is lexicographically less  ";
        cout << "than Gfg( case-insensitive )";

    } else {
        cout << "geeksforgeeks is not lexicographically less ";
        cout << "than Gfg( case-insensitive )";
    }
}
```

输出:

```
geeksforgeeks is not lexicographically less than Gfg
geeksforgeeks is lexicographically less than Gfg( case-insensitive )
```

## 可能的应用

比较字符串一般可以用在字典中，我们需要按照字典顺序来放置单词。这方面的例子可以是在给定的一组词中找出在词典中排在第一位的词。

```cpp
// C++ code to demonstrate the application of 
// lexicographical_compare()
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // initializing char arrays
    char list[][100]={
        {'a','b','a','c','u','s'},
        {'a','p','p','l','e'},
        {'c','a','r'},
        {'a','b','b','a'}
    };

    char min[100] = "zzzzzz";

    // using lexicographical_compare for checking 
    // the smallest
    for (int i=0; i<4; i++)
        if( lexicographical_compare(list[i], list[i]
                + strlen(list[i]), min, min+strlen(min)))       
             strcpy(min,list[i]);

    // prints "abacus"
    cout << "The smallest string is : ";
    for(int i = 0; min[i]!='\0'; i++)    
        cout<<min[i];     
}
```

输出:

```
The smallest string is : abacus
```

本文由 **Manjeet Singh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。