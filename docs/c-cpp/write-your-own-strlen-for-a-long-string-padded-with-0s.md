# 为用“\0”填充的长字符串编写自己的 strlen()

> 原文:[https://www . geesforgeks . org/write-your-your-strlen-for-long-string-padding-0s/](https://www.geeksforgeeks.org/write-your-own-strlen-for-a-long-string-padded-with-0s/)

给定一个表示字符串的大字符数组，使得所有尾随的非字符串字符在末尾都用“\0”填充，即所有前导字符都是字符串字符，所有尾随字符都是“\0”并且没有垃圾字符。写一个有效的函数来找到这样一个字符串的长度。

示例:

```cpp
Input: str[] = {'g', 'e', 'e', 'k', '\0', '\0', '\0', '\0', '\0', '\0'}
       n = 10  // Total no. of characters including \0's
Output: Length of string is 4     

Input: str[] = {'g', 'e', 'e', 'k', 's', 'q', 'u', 'i', 'z', '\0', '\0',
                  '\0', '\0', '\0', '\0', '\0'}
        n = 15
Output: Length of string is 9

```

一个简单的解决方案是像普通的 strlen 函数一样，我们一直读字符，直到我们遇到一个' \0 '。标准 strlen 的时间复杂度为 O(n)。

由于所有尾随字符都是' \0 '，我们可以使用[二分搜索法](https://www.geeksforgeeks.org/binary-search/)。
通过比较中间两个元素和' \0 '，我们可以决定我们是需要左半部分重现还是右半部分重现。
如果其中有一个是\0，那么我们找到了第一个出现。
否则如果两个元素都是' \0 '，那么我们需要移动到左半部分。
否则(当中间元素都不是\0 时)，我们需要移到右半部分。

下面是上述想法的 C 实现。

```cpp
// A Binary Search based implementation of strlen when all non-string
// characters are \0
#include <stdio.h>

/* if \0 is present in str[] then returns the index of FIRST occurrence
   of \0 in str[low..high], otherwise returns -1 */
int firstZero(char str[], int low, int high)
{
    if (high >= low)
    {
        // Check if mid element is first '\0'
        int mid = low + (high - low)/2;
        if (( mid == 0 || str[mid-1] != '\0') && str[mid] == '\0')
            return mid;

        if (str[mid] != '\0')  // If mid element is not '\0'
            return firstZero(str, (mid + 1), high);
        else  // If mid element is '\0', but not first '\0'
            return firstZero(str, low, (mid -1));
    }
    return -1;
}

// This function mainly calls firstZero to find length.
int myStrlen(char str[], int n)
{
    // Find index of first zero in given stray
    int first = firstZero(str, 0, n-1);

    // If '\0' is not present at all, return n
    if (first == -1)
        return n;

    return first;
}

/* Driver program to check above functions */
int main()
{
    char str[] =  {'g', 'e', 'e', 'k', 's', 'q', 'u', 'i', 'z', '\0', '\0',
                  '\0', '\0', '\0', '\0', '\0'};
    int n = sizeof(str)/sizeof(str[0]);
    printf("Length of string is %d", myStrlen(str, n));
    return 0;
}
```

输出:

```cpp
Length of string is 9
```

这个想法类似于下面的帖子。我们为第一次出现的“\0”做二分搜索法。
[求零的个数](https://www.geeksforgeeks.org/find-number-zeroes/)
[计算排序数组中出现的次数](https://www.geeksforgeeks.org/count-number-of-occurrences-in-a-sorted-array/)

上述解的时间复杂度为 O(Logn)，采用的算法范式为[分治](https://www.geeksforgeeks.org/tag/divide-and-conquer/)。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。