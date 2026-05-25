# 借助字符串数组中给定的模式搜索字符串

> 原文: [https://www.geeksforgeeks.org/search-strings-with-the-help-of-given-pattern-in-an-array-of-strings/](https://www.geeksforgeeks.org/search-strings-with-the-help-of-given-pattern-in-an-array-of-strings/)

**先决条件:** [Trie（插入并搜索）](https://www.geeksforgeeks.org/trie-insert-and-search/)

给定一个字符串的[数组](https://www.geeksforgeeks.org/introduction-to-arrays/) `words[]` 和一个部分字符串 `str`，任务是从给定的字符串数组中找到给定形式的字符串 `str`。

> 部分字符串是缺少某些字符的字符串。例如：`"..ta"`，是一个长度为 4 的字符串，以 `"ta"` 结尾，在索引 `0` 和 `1` 处缺少两个字符。

**示例:**

> **输入:** `words[] = ["moon", "soon", "mon", "sun", "data"]`, `str = "..on"`
> **输出:** `["moon", "soon"]`
> **解释:**
> `"moon"` 和 `"soon"` 匹配给定的偏串 `"..on"`
>
> **输入:** `words[] = ["date", "data", "month"]`, `str = "d.t."`
> **输出:** `["date", "data"]`
> **解释:**
> `"date"` 和 `"data"` 与给定的部分字符串 `"d.t."` 匹配

## 进场

**Trie 节点的结构:** 想法是使用 Trie 来解决给定的问题。下面是 Trie 的步骤和结构：

```
struct TrieNode 
{
     struct TrieNode* children[26];
     bool endOfWord;
};
```

下图解释了使用上例中给出的键构建 trie 的过程：

```
           root
      /     |      \
     d      m       s
     |      |       |
     a      o       o
     |      |  \    |
     t      o   n   o
  /  |      |   |   |
 e   a     n   t   n
                |
                h
```

每个节点都是一个 `TrieNode`，根据添加的单词，指针链接到后续的子节点。不存在字符的其他指针位置的值用空标记。`endOfWord` 用蓝色或叶节点表示。

## 步骤

1.  使用 `addWord()` 方法将所有可用的单词插入 trie 结构。
2.  要添加的单词的每个字符都作为一个单独的 `TrieNode` 插入。子数组是由 `26` 个 `TrieNode` 指针组成的数组。
3.  每个索引代表英语字母表中的一个字符。如果添加了一个新单词，那么对于每个字符，必须检查该字母表的 `TrieNode` 指针是否存在，然后继续下一个字符，如果不存在，则创建一个新的 `TrieNode`，并使指针指向该新节点，并且对该新节点处的下一个字符重复该过程。对于最后一个字符的 `TrieNode` 指针所指向的 `TrieNode`，`endOfWord` 被设为 `true`。
4.  要搜索关键字，请检查在由字符标记的索引处是否存在 `TrieNode`。如果存在，我们向下移动分支，对下一个字符重复这个过程。类似地搜索部分字符串，如果 `'.'` 找到后，我们在子数组中查找所有可用的 `TrieNode` 指针，并继续处理由索引标识的每个字符，占据 `'.'` 的位置一次。
5.  如果指针位置在任何一点都是空的，我们返回未找到。否则在最后一个 `TrieNode` 检查 `endOfWord`，如果为 `false`，我们返回未找到，否则单词被找到。

下面是上述方法的实现：

## C++

```
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Dictionary Class
class Dictionary {
public:
    // Initialize your data structure
    Dictionary* children[26];
    bool endOfWord;

    // Constructor
    Dictionary()
    {
        this->endOfWord = false;
        for (int i = 0; i < 26; i++) {
            this->children[i] = NULL;
        }
    }

    // Adds a word into a data structure
    void addWord(string word)
    {
        // Crawl pointer points the object
        // in reference
        Dictionary* pCrawl = this;

        // Traverse the given array of words
        for (int i = 0; i < word.length(); i++) {
            int index = word[i] - 'a';
            if (!pCrawl->children[index])
                pCrawl->children[index]
                    = new Dictionary();

            pCrawl = pCrawl->children[index];
        }
        pCrawl->endOfWord = true;
    }

    // Function that returns if the word
    // is in the data structure or not

    // A word can contain a dot character '.'
    // to represent any one letter
    void search(string word, bool& found,
                string curr_found = "",
                int pos = 0)
    {
        Dictionary* pCrawl = this;

        if (pos == word.length()) {
            if (pCrawl->endOfWord) {
                cout << "Found: "
                     << curr_found << "\n";
                found = true;
            }
            return;
        }

        if (word[pos] == '.') {

            // Iterate over every letter and
            // proceed further by replacing
            // the character in place of '.'
            for (int i = 0; i < 26; i++) {
                if (pCrawl->children[i]) {
                    pCrawl
                        ->children[i]
                        ->search(word,
                                 found,
                                 curr_found + char('a' + i),
                                 pos + 1);
                }
            }
        }
        else {

            // Check if pointer at character
            // position is available,
            // then proceed
            if (pCrawl->children[word[pos] - 'a']) {
                pCrawl
                    ->children[word[pos] - 'a']
                    ->search(word,
                             found,
                             curr_found + word[pos],
                             pos + 1);
            }
        }
        return;
    }

    // Utility function for search operation
    void searchUtil(string word)
    {
        Dictionary* pCrawl = this;

        cout << "\nSearching for \""
             << word << "\"\n";
        bool found = false;
        pCrawl->search(word, found);
        if (!found)
            cout << "No Word Found...!!\n";
    }
};

// Function that search the given pattern
void searchPattern(string arr[], int N,
                   string str)
{
    // Object of the class Dictionary
    Dictionary* obj = new Dictionary();

    for (int i = 0; i < N; i++) {
        obj->addWord(arr[i]);
    }

    // Search pattern
    obj->searchUtil(str);
}

// Driver Code
int main()
{
    // Given an array of words
    string arr[] = { "data", "date", "month" };

    int N = 3;

    // Given pattern
    string str = "d.t.";

    // Function Call
    searchPattern(arr, N, str);
}
```

**Output:**

```
Searching for "d.t."
Found: data
Found: date
```

时间复杂度: `O(M*log(N))`，其中 `N` 为字符串数，`M` 为给定模式的长度
辅助空间: `O(26*M)`