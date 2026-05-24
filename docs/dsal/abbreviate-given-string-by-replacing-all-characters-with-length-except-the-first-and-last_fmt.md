# 通过用长度替换除第一个和最后一个以外的所有字符来缩写给定的字符串

> 原文: [https://www.geeksforgeeks.org/abbreviate-given-string-by-replacing-all-characters-with-length-except-the-first-and-last/](https://www.geeksforgeeks.org/abbreviate-given-string-by-replacing-all-characters-with-length-except-the-first-and-last/)

给定字符串 `str`，任务是将给定的字符串转换成它的缩写形式：第一个字符，第一个和最后一个字符之间的字符数，以及字符串的最后一个字符。

**示例：**

> **输入：** `str = "internationalization"`
> **输出：** `i18n`
> **解释：** 第一个字母`'i'`，后面是`'i'`和`'n'`之间的字母数，即 18，最后一个字母`'n'`。
>
> **输入：** `str = "geeksforgeeks"`
> **输出：** `g11s`

**方法：** 给定的问题是基于实现的问题，可以通过以下步骤解决：

- 打印给定字符串 `str[0]` 的第一个字符。
- 将字符串的长度存储在变量 `len` 中，并打印 `len - 2`。
- 打印字符串的最后一个字符，即 `str[len - 1]`。

下面是上述方法的实现：

## C++

```cpp
// C++ program of the above approach
#include <iostream>
using namespace std;

// Function to convert the given
// string into its abbreviation
void abbreviateWord(string str)
{
    // Stores the length of the string
    int len = str.size();

    // Print 1st character
    cout << str[0];

    // Print count of characters
    // in between
    cout << len - 2;

    // Print last character
    cout << str[len - 1];
}

// Driver Code
int main()
{
    string str = "internationalization";
    abbreviateWord(str);

    return 0;
}
```

**输出**

```
i18n
```

**时间复杂度：** `O(1)`
**辅助空间：** `O(1)`