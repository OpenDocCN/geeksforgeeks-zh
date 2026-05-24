# C++ 程序检查一个字符串是否是 Pangram

> 原文:[https://www . geesforgeks . org/c-program-to-check-a-string-is-pangram-or-not/](https://www.geeksforgeeks.org/c-program-to-check-whether-a-string-is-a-pangram-or-not/)

给定字符串 **str，**任务是检查一个字符串在 C++ 中是否是 pangram 使用。

> 如果一个[字符串包含所有的英文字母，那么这个字符串就是一个 Pangram](https://www.geeksforgeeks.org/pangram-checking/) 。

**示例:**

> **输入:str =**我们及时判断古董象牙扣为下一个奖品”
> 
> **输出:**是
> 
> **说明:**在上面的字符串中，str 有所有的英文字母。
> 
> **输入:str =**我们及时判定古董象牙扣为奖品“
> 
> **输出:**否

### ****<u>方法-1:不使用 STL</u>****

**这种方法基于哈希。**

1.  **创建一个大小为 26 的布尔类型的哈希数据结构，这样索引 0 代表字符“a”，1 代表字符“b”等等。**
2.  **逐个字符遍历字符串，并将特定字符标记为哈希中存在的字符。**
3.  **在完成字符串的遍历和标记后，遍历哈希并查看是否所有字符都存在，即每个索引都为真。如果都标记了，那么返回真，否则返回假。**

**以下是上述方法的实现:**

## **C++**

```cpp
// C++ Program to check if the given
// string is a pangram or not

#include <bits/stdc++.h>
using namespace std;

// Returns true if the string is
// pangram else false
bool checkPangram(string& str)
{
    // Create a hash table to mark
    // the characters
    // present in the string
    vector<bool> mark(26, false);

    // For indexing in mark[]
    int index;

    // Traverse all characters
    for (int i = 0; i < str.length(); i++) {

        // If uppercase character,
        // subtract 'A' to find index.
        if ('A' <= str[i] && str[i] <= 'Z')
            index = str[i] - 'A';

        // If lowercase character,
        // subtract 'a' to find index.
        else if ('a' <= str[i]
                 && str[i] <= 'z')
            index = str[i] - 'a';

        // If this character is not
        // an alphabet, skip to next one.
        else
            continue;

        mark[index] = true;
    }

    // Return false
    // if any character is unmarked
    for (int i = 0; i <= 25; i++)
        if (mark[i] == false)
            return (false);

    // If all characters were present
    return (true);
}

// Driver Code
int main()
{
    string str = "We promptly judged"
                 " antique ivory"
                 " buckles for the next prize";

    if (checkPangram(str) == true)
        printf("Yes");
    else
        printf("No");

    return (0);
}
```

****Output**

```cpp
Yes
```** 

****时间复杂度:** *O(N)，其中 N 为*即*弦的*长度。*
**辅助空间:** *O(1)****

### ****<u>方法-2:使用</u>**[**<u>STL</u>**](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/)**

**STL 的[变换()方法可以用来检查给定的字符串是否是 Pangram。](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/)**

****语法:****

> **transform(s.begin()、s.end()、s.begin()、::toupper)；**

****方法:**
为了检查字符串是否包含英语字母表中的所有字母:**

> ****第一步:**首先将所有字母转换成大写或小写，因为如果不转换就检查，小写字母和大写字母会被认为是不同的字母。
> **第二步:**对字符串进行排序，并检查不同的字母。
> **第三步:**空间也会被认为是一个截然不同的实体。
> **步骤 4:** 现在检查计数是否=27，然后字符串包含所有 26 个字母。**

**以下是上述方法的实现:**

## **卡片打印处理机（Card Print Processor 的缩写）**

```cpp
// C++ Program to check whether
// a string pangram or not using STL

#include <bits/stdc++.h>
using namespace std;

// Function to return given string
// str is pangrams yes or no
string pangrams(string s)
{

    // Initialization of count
    int count = 0;

    // Convert each letter into
    // uppercase to avoid counting
    // of both uppercase and
    // lowercase as different letters
    transform(s.begin(),
              s.end(),
              s.begin(),
              ::toupper);

    // Sort the string
    sort(s.begin(), s.end());

    // Count distinct alphabets
    for (int i = 0; i < s.size(); i++) {
        if (s[i] != s[i + 1])
            count++ ;
    }

    // If count is 27 then the string
    // contains all the alphabets
    // including space as a
    // distinct character
    if (count == 27)
        return "Yes";

    else
        return "No";
}

// Driver code
int main()
{
    // Given string str
    string str = "We promptly "
                 "judged antique"
                 "ivory buckles for "
                 "the next prize";

    // Function Call
    cout << pangrams(str);

    return 0;
}
```

****Output**

```cpp
Yes
```** 

****时间复杂度:** *O(N)，其中 N 为*即*弦的*长度。*
**辅助空间:** *O(1)****