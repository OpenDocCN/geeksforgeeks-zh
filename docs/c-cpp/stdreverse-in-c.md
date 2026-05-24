# std::reverse()在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdreverse-in-c/](https://www.geeksforgeeks.org/stdreverse-in-c/)

reverse()是头文件算法中的预定义函数。它被定义为上述头文件中的一个模板。它颠倒任何容器的范围[第一个，最后一个]中元素的顺序。时间复杂度为 O(n)。
**注意:**使用的范围是【第一个，最后一个】，包含第一个和最后一个之间的所有元素，包括第一个指向的元素，但不包括最后一个指向的元素。
**语法:**

```cpp
void reverse(BidirectionalIterator first, BidirectionalIterator last)
BidirectionalIterator is an iterator that can be used to access any
elements of a container in both forward and backward direction.
```

**示例:**

```cpp
Input : 10 11 12 13 14 15 16 17
Output :10 11 12 13 14 17 16 15
Explanation:
reverse(v.begin() + 5, v.begin() + 8);
In the above function, input we have applied reverse() on the vector
from index 5 to index 7.
Therefore when we display the vector we get reverse order
from index 5 to index 7.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std::reverse() function of STL
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> vec1;
    vector<int>::iterator p;

    // Inserting elements in vector
    for (int i = 0; i < 8; i++) {
        vec1.push_back(i + 10);
    }
    // Displaying elements of vector
    cout<<"Initial Vector:"<<endl;
    for(p = vec1.begin(); p < vec1.end(); p++) {
        cout << *p << " ";
    }
    cout << endl;

    cout << "Reverse only from index 5 to 7 in vector:\n";
    // Reversing elements from index 5 to index 7
    reverse(vec1.begin() + 5, vec1.begin() + 8);

    // Displaying elements of vector after Reversing
    for (p = vec1.begin(); p < vec1.end(); p++) {
        cout << *p << " ";
    }
    cout << endl <<endl;

    vector<int> vec2{ 4, 5, 6, 7 };

    cout<<"Initial Vector:"<<endl;
    for (p = vec2.begin(); p < vec2.end(); p++) {
        cout << *p << " ";
    }
    cout << endl;

    cout << "Reverse full Vector:"<<endl;
    // Reversing directly from beginning to end
    reverse(vec2.begin(), vec2.end());

    // Displaying elements of vector after Reversing
    for (p = vec2.begin(); p < vec2.end(); p++) {
        cout << *p << " ";
    }
    cout << endl;

    return 0;
}
```

**输出:**

```cpp
Initial Vector:
10 11 12 13 14 15 16 17 
Reverse only from index 5 to 7 in vector:
10 11 12 13 14 17 16 15 

Initial Vector:
4 5 6 7 
Reverse full Vector:
7 6 5 4 
```

**时间复杂度:** O(n)

本文由 **Hardik Gaur** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。