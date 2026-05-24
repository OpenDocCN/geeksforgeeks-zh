# 使用 STL 函数

查找并打印 std::vector <string>中的重复单词</string>

> 原文:[https://www . geesforgeks . org/find-print-duplicate-words-stdvectorstring-using-STL-functions/](https://www.geeksforgeeks.org/find-print-duplicate-words-stdvectorstring-using-stl-functions/)

考虑一个字符串数组，并在该数组中找到重复的单词，如果存在重复的单词，则打印出来。
示例:

```cpp
Input : { "welcome", "to", "geeks", "for", "geeks" }
Output : geeks

Input : { "reduce", "reuse", "recycle", "reduce", 
          "reuse", "recycle", " recycle" }
Output : recycle
reduce
reuse

Input : { "Go", "Green" }
Output : No Duplicate words
```

**方法 1(使用排序)**
1。字符串的排序数组。
2。比较字符串数组中相邻单词。
3。如果两个单词相同，则将该单词推入另一个向量串。
4。打印重复的单词(如果存在)。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to find duplicate word in a
// vector<string>
#include <bits/stdc++.h>
using namespace std;

void printDuplicates(vector<string> words)
{
    vector<string> duplicate;

    // STL function to sort the array of string
    sort(words.begin(), words.end());

    for (int i = 1; i < words.size(); i++) {
        if (words[i - 1] == words[i]) {

            // STL function to push the duplicate
            // words in a new vector string
            if (duplicate.empty())
              duplicate.push_back(words[i]);
            else if (words[i] != duplicate.back())
                duplicate.push_back(words[i]);
        }
    }

    if (duplicate.size() == 0)
        cout << "No Duplicate words" << endl;
    else
        for (int i = 0; i < duplicate.size(); i++)
            cout << duplicate[i] << endl;
}

// Driver code
int main()
{
    vector<string> words{ "welcome", "to", "geeks", "for",
                          "geeks",   "to", "geeks" };
    printDuplicates(words);
    return 0;
}
```

**Output**

```cpp
geeks
to

```