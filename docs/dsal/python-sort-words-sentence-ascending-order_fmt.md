# Python | 按升序排列句子单词

> 原文: [https://www.geeksforgeeks.org/python-sort-words-sentence-ascending-order/](https://www.geeksforgeeks.org/python-sort-words-sentence-ascending-order/)

给定一个句子，按字母升序排序。

## 示例

```
Input : to learn programming refer geeksforgeeks
Output : geeksforgeeks learn programming refer to

Input : geeks for geeks
Output : for geeks geeks
```

我们将使用内置的库函数按升序对句子中的单词进行排序。

## 先决条件

1.  [`split()`](https://www.geeksforgeeks.org/how-to-split-a-string-in-cc-python-and-java/)
2.  [`sort()`](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/) in Python
3.  [`join()`](https://www.geeksforgeeks.org/join-function-python/)

## 算法步骤

*   把句子分成单词。
*   按字母顺序排列单词。
*   将排序后的单词按字母顺序连接起来，组成一个新句子。

## 代码实现

下面是上面思路的实现。

```python
# Function to sort the words
# in ascending order
def sortedSentence(Sentence):

    # Splitting the Sentence into words
    words = Sentence.split(" ")

    # Sorting the words
    words.sort()

    # Making new Sentence by
    # joining the sorted words
    newSentence = " ".join(words)

    # Return newSentence
    return newSentence

# Driver's Code

Sentence = "to learn programming refer geeksforgeeks"
# Print the sortedSentence
print(sortedSentence(Sentence))

Sentence = "geeks for geeks"
# Print the sortedSentence
print(sortedSentence(Sentence))
```

## 输出

```
geeksforgeeks learn programming refer to
for geeks geeks
```