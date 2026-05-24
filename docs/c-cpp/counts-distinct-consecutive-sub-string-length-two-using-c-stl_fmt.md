# 使用 C++ STL 对长度为 2 的不同连续子串进行计数

> 原文：[https://www.geeksforgeeks.org/counts-distinct-consecutive-sub-string-length-two-using-c-stl/](https://www.geeksforgeeks.org/counts-distinct-consecutive-sub-string-length-two-using-c-stl/)

给定一个字符串，任务是打印给定字符串中长度为 2 的所有不同子字符串。所有子字符串都应该按照字典顺序打印。

## 示例

```cpp
Input: str = "abcab"
Output: ab-2
        bc-1
        ca-1

Input: str = "xyz"
Output: xy-1
        yz-1
```

## 本文的思路

本文的思路是在 C++ STL 中演示`映射`和`对`。
我们声明一个映射`d_pairs`，它使用一个字符对作为键并作为值计数。我们从起始索引开始迭代给定的字符串，以存储每个连续的对（如果还没有出现的话），并在映射中增加其计数。循环完成后，我们在映射容器中获得所有不同的连续对及其对应的出现次数。
请注意，我们需要按排序顺序输出，因此使用了`map`。如果不需要按排序顺序输出，我们可以使用`unordered_map()`。`unordered_map()`运算的时间复杂度为`O(1)`，而`map`的时间复杂度为`O(log n)`。

## 代码实现

```cpp
// C++ STL based program to print all distinct
// substrings of size 2 and their counts.
#include<bits/stdc++.h>
using namespace std;

void printDistinctSubStrs(string str)
{
    // Create a map to store unique substrings of
    // size 2
    map<pair<char,char>, int> dPairs;

    // Count occurrences of all pairs
    for (int i=0; i<str.size()-1; i++)
        dPairs[make_pair(str[i], str[i+1])]++ ;

    // Traverse map to print sub-strings and their
    // counts.
    cout << "Distinct sub-strings with counts:\n";
    for (auto it=dPairs.begin(); it!=dPairs.end(); it++)
        cout << it->first.first << it->first.second
             << "-" << it->second << " ";
}

// Driver code
int main()
{
    string str = "abcacdcacabacaassddssklac";
    printDistinctSubStrs(str);
    return 0;
}
```

## 输出

```cpp
Distinct sub-strings with counts:
aa-1 ab-2 ac-4 as-1 ba-1 bc-1 ca-4 cd-1 dc-1 dd-1 ds-1 kl-1 la-1 sd-1 sk-1 ss-2 
```

本文由**希曼舒·古普塔(巴格里)**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。