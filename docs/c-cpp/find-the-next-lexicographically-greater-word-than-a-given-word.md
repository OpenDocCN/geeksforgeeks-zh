# c++ 中字典顺序下一个排列

> 原文:[https://www . geesforgeks . org/find-the-next-按字典顺序大于给定单词/](https://www.geeksforgeeks.org/find-the-next-lexicographically-greater-word-than-a-given-word/)

给定一个单词，找到它在词典上更大的排列。例如，从词典的角度来看，“gfg”的下一个排列是“ggf”，而“acb”的下一个排列是“bac”。

注意:在某些情况下，下一个字典上更大的单词可能不存在，例如，“aaa”和“edcba”

在 C++ 中，有一个特定的函数可以省去我们很多代码。它在文件#include <algorithm>中。函数是 next _ arrange(a . begin()、a.end())。如果函数可以将对象重新排列为字典上更大的排列，则返回“真”。否则，该函数返回“false”。</algorithm>

让我们看看这里的代码片段:

```cpp
// Find the next lexicographically
// greater permutation of a word

#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    string s = { "gfg" };
    bool val
        = next_permutation(s.begin(),
                           s.end());
    if (val == false)
        cout << "No Word Possible"
             << endl;
    else
        cout << s << endl;
    return 0;
}
```

**Output:**

```cpp
ggf

```

同样的程序也可以**实现，无需使用 STL** 。下面是相同的代码片段。这个想法是基于以下事实:
1)按降序排列的一个序列没有下一个排列。例如 edcba "没有下一个排列。
2)对于未按降序排序的序列，例如“abedc”，我们可以遵循以下步骤。
…………。a)从右开始遍历，找到第一个不按降序排列的项目。例如，在“abedc”中，字符“b”不遵循降序。
……。b)将找到的字符与其右侧最接近的较大(或最小较大)元素交换。在“abedc”的情况下，我们将“c”作为最接近的较大元素。交换“b”和“c”后，字符串变成“acedb”。
………。c)交换后，在步骤 **a** 中找到的字符位置后对字符串进行排序。对“acedb”的子串“edb”排序后，得到“ **acbde** ”，这是需要的下一个排列。

步骤 b)和 c)
a)中的优化由于序列是按降序排序的，所以我们可以使用二分搜索法来找到最近的较大元素。
c)由于序列已经按降序排序(即使在交换之后，因为我们交换了最接近的大的序列)，所以我们可以在反转后按升序排序序列。

```cpp
// Find the next lexicographically
// greater permutation of a word

#include <iostream>

using namespace std;

void swap(char* a, char* b)
{
    if (*a == *b)
        return;
    *a ^= *b;
    *b ^= *a;
    *a ^= *b;
}
void rev(string& s, int l, int r)
{
    while (l < r)
        swap(&s[l++ ], &s[r--]);
}

int bsearch(string& s, int l, int r, int key)
{
    int index = -1;
    while (l <= r) {
        int mid = l + (r - l) / 2;
        if (s[mid] <= key)
            r = mid - 1;
        else {
            l = mid + 1;
            if (index == -1 || s[index] >= s[mid])
                index = mid;
        }
    }
    return index;
}

bool nextpermutation(string& s)
{
    int len = s.length(), i = len - 2;
    while (i >= 0 && s[i] >= s[i + 1])
        --i;
    if (i < 0)
        return false;
    else {
        int index = bsearch(s, i + 1, len - 1, s[i]);
        swap(&s[i], &s[index]);
        rev(s, i + 1, len - 1);
        return true;
    }
}

// Driver code
int main()
{
    string s = { "gfg" };
    bool val = nextpermutation(s);
    if (val == false)
        cout << "No Word Possible" << endl;
    else
        cout << s << endl;
    return 0;
}
// This code is contributed by Mysterious Mind
```

**Output:**

```cpp
ggf

```

**时间复杂度:**

1.  在最坏的情况下，next _ 置换的第一步需要 O(n)个时间。
2.  二分搜索法需要时间。
3.  反向需要 0(n)时间。

**整体时间复杂度为 O(n)。**
其中 n 是字符串的长度。

**参考:**T2【http://www . cplusplus . com/Reference/algorithm/next _ arrange/

本文由**哈什特·古普塔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。