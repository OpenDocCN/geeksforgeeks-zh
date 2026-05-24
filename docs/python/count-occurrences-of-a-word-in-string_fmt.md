# 统计字符串中某个单词的出现次数

> 原文：[https://www.geeksforgeeks.org/count-occurrences-of-a-word-in-string/](https://www.geeksforgeeks.org/count-occurrences-of-a-word-in-string/)

给你一个字符串和一个单词，你的任务是计算字符串中给定单词的出现次数，并打印单词的出现次数。

## 示例

```py
Input : string = "GeeksforGeeks A computer science portal for geeks"
word = "portal"
Output : Occurrences of Word = 1 Time

Input : string = "GeeksforGeeks A computer science portal for geeks"
word = "technical" 
Output : Occurrences of Word = 0 Time
```

## 方法一：遍历比较

### 思路

*   首先，我们将字符串按空格分割成单词列表。
*   然后，取一个变量 `count = 0`，在每一个匹配成功的条件下，我们将计数增加 1。
*   现在运行一个从 0 到字符串长度的循环，检查列表中的单词是否等于目标单词。
*   如果条件为真，那么我们将 `count` 的值增加 1，最后打印 `count` 的值。

下面是上述方法的实现：

### C++

```cpp
// C++ program to count the number
// of occurrence of a word in
// the given string
#include <bits/stdc++.h>
using namespace std;

int countOccurrences(char *str,
                     string word)
{
    char *p;

    // split the string by spaces in a
    vector<string> a;

    p = strtok(str, " ");
    while (p != NULL)
    {
        a.push_back(p);
        p = strtok(NULL, " ");
    }

    // search for pattern in a
    int c = 0;
    for (int i = 0; i < a.size(); i++)

        // if match found increase count
        if (word == a[i])
            c++;
    return c;
}

// Driver code
int main()
{
    char str[] = "GeeksforGeeks A computer science portal for geeks ";
    string word = "portal";
    cout << countOccurrences(str, word);
    return 0;
}

// This code is contributed by
// sanjeev2552
```

### Java

```java
// Java program to count the number
// of occurrence of a word in
// the given string
import java.io.*;

class GFG {

static int countOccurrences(String str, String word)
{
    // split the string by spaces in a
    String a[] = str.split(" ");

    // search for pattern in a
    int count = 0;
    for (int i = 0; i < a.length; i++)
    {
    // if match found increase count
    if (word.equals(a[i]))
        count++;
    }

    return count;
}

// Driver code
public static void main(String args[])
{
    String str = "GeeksforGeeks A computer science portal for geeks ";
    String word = "portal";
    System.out.println(countOccurrences(str, word));
}
}

/*This code is contributed by Nikita Tiwari.*/
```

### Python 3

```python
# Python program to count the number of occurrence
# of a word in the given string

def countOccurrences(str, word):

    # split the string by spaces in a
    a = str.split(" ")

    # search for pattern in a
    count = 0
    for i in range(0, len(a)):

        # if match found increase count
        if (word == a[i]):
           count = count + 1

    return count      

# Driver code
str ="GeeksforGeeks A computer science portal for geeks  "
word ="portal"
print(countOccurrences(str, word))
```

### C#

```csharp
// C# program to count the number
// of occurrence of a word in
// the given string
using System;

class GFG
{
static int countOccurrences(string str,
                            string word)
{
    // split the string by spaces
    string[] a = str.Split(' ');

    // search for pattern in string
    int count = 0;
    for (int i = 0; i < a.Length; i++)
    {

    // if match found increase count
    if (word.Equals(a[i]))
        count++;
    }

    return count;
}

// Driver code
public static void Main()
{
    string str = "GeeksforGeeks A computer science portal for geeks ";
    string word = "portal";
    Console.Write(countOccurrences(str, word));
}
}

// This code is contributed
// by ChitraNayal
```

### PHP

```php
<?php
// PHP program to count the number
// of occurrence of a word in
// the given string

function countOccurrences($str, $word)
{
    // split the string by spaces
    $a = explode(" ", $str);

    // search for pattern in string
    $count = 0;
    for ($i = 0; $i < sizeof($a); $i++)
    {

    // if match found increase count
    if ($word == $a[$i])
        $count++;
    }

    return $count;
}

// Driver code
$str = "GeeksforGeeks A computer science portal for geeks ";
$word = "portal";
echo (countOccurrences($str, $word));

// This code is contributed
// by ChitraNayal
?>
```

### JavaScript

```javascript
<script>

// Javascript program to count the number
// of occurrence of a word in
// the given string

    function countOccurrences(str,word)
    {
        // split the string by spaces in a
    let a = str.split(" ");

    // search for pattern in a
    let count = 0;
    for (let i = 0; i < a.length; i++)
    {
    // if match found increase count
    if (word==(a[i]))
        count++;
    }

    return count;
    }
    // Driver code
    let str = "GeeksforGeeks A computer science portal for geeks ";
    let word = "portal";
    document.write(countOccurrences(str, word));

    // This code is contributed by avanitrachhadiya2155

</script>
```

**输出:**

```text
1
```

## 方法二：使用 Python 中的 `count()` 函数

### 思路

*   首先，我们用空格分割字符串并存储在列表中。
*   我们使用 `count()` 来查找列表中单词出现的次数。

下面是实现：

### Python 3

```python
# Python program to count the number of occurrence
# of a word in the given string
def countOccurrences(str, word):

    wordslist = list(str.split())
    return wordslist.count(word)

# Driver code
str = "GeeksforGeeks A computer science portal for geeks  "
word = "portal"
print(countOccurrences(str, word))

# This code is contributed by vikkycirus
```

**输出**

```text
1
```

参考：[split() 函数 Python](https://www.geeksforgeeks.org/how-to-split-a-string-in-cc-python-and-java/)