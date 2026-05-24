# 生成句子中所有可能的单词排列

> 原文: [https://www.geeksforgeeks.org/generate-all-possible-permutations-of-words-in-a-sentence/](https://www.geeksforgeeks.org/generate-all-possible-permutations-of-words-in-a-sentence/)

给定一个[字符串](https://www.geeksforgeeks.org/string-data-structure/) `S`，任务是打印一个句子中所有单词的[排列](https://www.geeksforgeeks.org/print-all-permutations-of-a-string-in-java/)。

## 示例

> **输入:** `S = "sky is blue"`
> **输出:**
> sky is blue
> sky blue is
> is sky blue
> is blue sky
> blue sky is
> blue is sky
>
> **输入:** `S = "do what you love"`
> **输出:**
> do what you love
> do what love you
> do you what love
> do you love what
> do love what you
> do love you what
> what do you love
> what do love you
> what you do love
> what you love do
> what love do you
> what love you do
> you do what love
> you do love what
> you what do love
> you what love do
> you love what do
> you love do what
> love what do you
> love what you do
> love you do what
> love you what do
> love do what you
> love do you what

## 方法

给定的问题可以使用[递归](https://www.geeksforgeeks.org/recursion/)来解决。按照以下步骤解决问题:

1.  [遍历句子](https://www.geeksforgeeks.org/split-a-sentence-into-words-in-cpp/)，使用 `split()` 将句子中出现的单词用空格分割，并存储在列表中。
2.  使用内置 Python 函数 `permutations()` 对列表进行置换。
3.  [遍历排列](https://www.geeksforgeeks.org/print-all-possible-permutations-of-an-array-with-duplicates-using-backtracking/)并将每个转换为 `list`。
4.  [打印这些列表](https://www.geeksforgeeks.org/print-lists-in-python-4-different-ways/)。

下面是上述方法的实现:

## Python 3

```python
# Python implementation of
# the above approach

from itertools import permutations

# Function to generate permutations
# of all words in a sentence
def calculatePermutations(sentence):

    # Stores all words in the sentence
    lis = list(sentence.split())

    # Stores all possible permutations
    # of words in this list
    permute = permutations(lis)

    # Iterate over all permutations
    for i in permute:

        # Convert the current
        # permutation into a list
        permutelist = list(i)

        # Print the words in the
        # list separated by spaces
        for j in permutelist:
            print(j, end = " ")

        # Print a new line
        print()

# Driver Code
if __name__ == '__main__':

    sentence = "sky is blue"
    calculatePermutations(sentence)
```

**输出:**

```
sky is blue 
sky blue is 
is sky blue 
is blue sky 
blue sky is 
blue is sky
```

***时间复杂度:** O(N!)，其中 N 表示一个句子中的字数。*
***辅助空间:** O(N!)*