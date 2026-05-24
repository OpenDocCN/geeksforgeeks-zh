# STD::is _ c++ STL 中的置换

> 原文:[https://www.geeksforgeeks.org/stdis_permutation-c-stl/](https://www.geeksforgeeks.org/stdis_permutation-c-stl/)

C++ 函数 STD::algorithm::is _ replacement()测试一个序列是否是其他序列的置换。它使用运算符==进行比较。这个函数是在 C++ 11 中定义的。
**语法:**

```cpp
template <class ForwardIterator1, class ForwardIterator2 >
bool is_permutation(ForwardIterator1 first1, ForwardIterator1 last1,
ForwardIterator2 first2);

first1, last1: Input iterators to the initial 
and final positions of the first sequence.
first2 : Input iterator to the initial position of the second sequence. 

Return value :
true : if all the elements in range [first1, last1] 
compare equal to those of the range
starting at first2 in any order.
false : Any element missing or exceeding.
```

该函数考虑这个序列中与[first1，last1]范围内的元素一样多的元素。如果该序列较短，会导致未定义的行为。

```cpp
// CPP program to check if 
// two arrays are equal or not
// using std :: is_permutation
#include <iostream>
#include <algorithm>

//Driver Code
int main()
{
    int A[] = {1, 7, 0, 2};
    int B[] = {0, 7, 2, 1};

    // Check if array B includes all elements of 
    // array A
    if ( std :: is_permutation ( A, A+4, B ) )
    {
        std :: cout << "B is a permutation of A" ;
    }

    else
    {
        std :: cout << "B is not a permutation of A" ;
    }
    return 0;
}
```

输出:

```cpp
B is a permutation of A

```

寻找数组是否相等的其他方法在这里讨论。

**另一个例子:检查两个字符串是否是彼此的字谜**

```cpp
// CPP program to check whether two strings 
// are anagram of each other
// using std :: is_permutation
#include <iostream>
#include <algorithm>

/*Driver Code*/
int main()
{
    std :: string A = "SILENT";
    std :: string B = "LISTEN";

    /*Checking if B is a permutation of A*/
    if ( is_permutation ( A.begin(), A.end(), B.begin() ) )
    {
        std :: cout << "Anagrams" ;
    }

    else
    {
        std :: cout << "Not Anagrams" ;
    }
    return 0;
}
```

输出:

```cpp
Anagrams

```

检查两个字符串是否是彼此的字谜的其他方法在这里讨论。

**标准版本::排列**

```cpp
template< class ForwardIt1, class ForwardIt2 >
bool is_permutation( ForwardIt1 first1, ForwardIt1 last1,
                     ForwardIt2 first2 );
// (since C++ 11)
template< class ForwardIt1, class ForwardIt2, class BinaryPredicate >
bool is_permutation( ForwardIt1 first1, ForwardIt1 last1,
                     ForwardIt2 first2, BinaryPredicate p );
// (since C++ 11)
template< class ForwardIt1, class ForwardIt2 >
bool is_permutation( ForwardIt1 first1, ForwardIt1 last1,
                     ForwardIt2 first2, ForwardIt2 last2 );
// (since C++ 14)
template< class ForwardIt1, class ForwardIt2, class BinaryPredicate >
bool is_permutation( ForwardIt1 first1, ForwardIt1 last1,
                     ForwardIt2 first2, ForwardIt2 last)2,
                     BinaryPredicate p );
//(since C++ 14)

first1, last1 : the range of elements to compare
first2, last2 : the second range to compare
p : binary predicate which returns ​true if the elements should be treated as equal.

```

示例:

```cpp
// False
is_permutation ( c1.begin(),     c1.end (), c2.begin(), c2.end ()) 

// True
is_permutation ( c1.begin() + 1, c1.end (), c2.begin(), c2.end ())

// True, all empty ranges are permutations of each other
is_permutation ( c1.end (), c1.end (), c2.end(), c2.end ())
```

**参考:**[STD 官方 C++ 文档::is _ arrangement](http://www.boost.org/doc/libs/1_64_0/libs/algorithm/doc/html/the_boost_algorithm_library/CXX11/is_permutation.html)

本文由 **[罗希特·塔普利亚尔](https://www.linkedin.com/in/rohit-thapliyal-515b5913a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。