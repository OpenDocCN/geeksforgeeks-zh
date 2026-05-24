# STD::c++ 中 get _ temporal _ buffer

> 原文:[https://www . geesforgeks . org/stdget _ temporary _ buffer-in-CPP/](https://www.geeksforgeeks.org/stdget_temporary_buffer-in-cpp/)

获取一块临时内存。在 C++ STL 库中，有一个函数**get _ temporal _ buffer**，主要用来获取一个临时块。

*   这个函数取一个大小为 n 的缓冲区，并返回大小为 n 的最大可用缓冲区，该缓冲区可以放入物理内存。
*   该函数用于获取临时内存，主要用于算法的操作，因为一些算法需要额外的空间来正确执行。
*   一旦分配的存储块不再需要，就应该通过调用**return _ 暂存 _buffer 来释放。**

**语法:**

```cpp
pair(int*, ptrdiff_t) p = get_temporary_buffer(int)(required size)
```

**参数:**

*   n:为其分配临时内存的 T 型元素的数量。
*   ptrdiff_t:它是一个整型。

**返回:**函数返回第一对和第二对对象。分配内存时，第一个包含指向块中第一个元素的指针，第二个包含大小。如果没有分配内存块，则第一对包含空指针，第二对包含零。

**示例 1:**
使用*get _ temporal _ buffer*对数组中的偶数总数进行计数并打印排序后的数组

```cpp
Input : 8, 9, 2, 1, 10, 14, 37, 18, 17, 5
Output : It contain 10 elements
        Sorted array is 1, 2, 5, 8, 9, 10, 14, 17, 18, 37
Explanation:
Step 1: initialize the array b[]
        first, we find the even number  elements in an array using for loop[0-n-1]
        if(a[i]%2==0){ c++ ;}
        print the count of even number.
Step 2: use get_temporary buffer to allocate the block of memory 
        pair(int*, ptrdiff_t) p=get_temporary_buffer(int)(required size)
        here required size is 10
Step 3: now copy the elements in the temporary buffer 
        uninitialized_copy(b, b+p.second, p.first);
        now using for loop [0 to p.second-1] sort the array using sort function 
        sort(p.first, p.first+p.second)
        and finally print the sorted array.
```

## C++

```cpp
// C++ code to demonstrate the get_temporary_buffer
// to sort an array

#include <iostream>
#include <algorithm>
#include <memory>
using namespace std;
void sorting(int b[], int n)
{
    int i, c = 0;
    for (i = 0; i < n; i++) {
        if (b[i] % 2 == 0) {
            c++ ;
        }
    }
    cout << "The total even numbers are:  " << c << endl;
    cout << "original array :"
         << " ";
    cout << "\n";
    for (i = 0; i < 10; i++) {
        cout << b[i] << " ";
    }
    cout << "\n";
    pair<int*, ptrdiff_t> p = get_temporary_buffer<int>(10);

    // copy the contents in temporary buffer with pair
    uninitialized_copy(b, b + p.second, p.first);

    sort(p.first, p.first + p.second);

    cout << "sorted array :" << endl;
    for (i = 0; i < p.second; i++) {
        cout << p.first[i] << " ";
    }
}
// driver program to test above function
int main()
{
    int b[] = { 8, 9, 2, 1, 10, 14, 37, 18, 17, 5 };
    int n = sizeof(b) / sizeof(b[0]);
    sorting(b, n);
    return 0;
}
```

**输出:**

```cpp
The total even numbers are: 5
original array : 
8 9 2 1 10 14 37 18 17 5 
sorted array :
1 2 5 8 9 10 14 17 18 37
```

**示例 2:**
使用 get _ temporary _ buffer 和 return _ temporary _ buffer 对字符串进行字母排序

```cpp
Input : 'b', 'g', 'y', 'v', 'p'
Output : b g p v y 
This will print the contents in an increasing order of alphabets. 
```

## C++

```cpp
// C++ code to sort the characters
// alphabetically using std::get_temporary_buffer
#include <iostream>
#include <algorithm>
#include <memory>
#include <string.h>
using namespace std;
void sorting(char b[], int n)
{
    int i;
    pair<char*, ptrdiff_t> p = get_temporary_buffer<char>(n);

    // copy the contents in temporary buffer with pair
    uninitialized_copy(b, b + p.second, p.first);

    // sort char array
    sort(p.first, p.first + p.second);

    cout << "sorted characters are :" << endl;
    for (i = 0; i < p.second; i++) {
        cout << p.first[i] << " ";
    }

    // to release the temporary buffer
    return_temporary_buffer(p.first);
}
// driver program to test above function
int main()
{
    char str[] = { 'b', 'g', 'y', 'v', 'p' };
    int c;
    c = strlen(str);

    sorting(str, c);
    return 0;
}
```

**Output**

```cpp
sorted characters are :
b g p v y  
```

**应用:**算法通常需要临时空间才能正确执行。它有一个非常特殊的用途，在类似 [stable_partition](https://www.geeksforgeeks.org/stdstable_partition-in-c/) 、stable_sort 和 [inplace_merge](https://www.geeksforgeeks.org/merge-operations-using-stl-in-c-merge-includes-set_union-set_intersection-set_difference/) 这样的算法中，STL 内部使用它们使用额外的临时内存来存储中间结果，如果有额外的内存，它们的运行时复杂性会更好。

本文由**希瓦尼·巴盖尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。