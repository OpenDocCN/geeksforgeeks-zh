# C# 估算句子中“是”字出现频率的程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-estate-frequency-of-word-in-in-a-句子/](https://www.geeksforgeeks.org/c-sharp-program-to-estimate-the-frequency-of-the-word-is-in-a-sentence/)

给定一个字符串作为输入，我们需要用 C# 编写一个程序来计算字符串中“is”这个词的出现频率。该程序的任务是统计字符串中给定单词“is”的出现次数，并打印“is”的出现次数。

**示例:**

> **输入:** string =“准备面试最简单的方法就是在 GeeksforGeeks 这个最好的计算机科学门户上练习。”
> 
> **输出:**出现“是”= 2 次
> 
> **输入:** string =“这是和姐姐说话的方式吗？我不知道那是什么”
> 
> **输出:**出现“是”= 3 次
> 
> **解释:**这个“是”在“姐姐”和“这个”这两个词中也出现过，但我们要找的是“是”这两个词分别出现。因此只有 3 次。

**使用迭代方法**

**进场:**

> 1.  Splitting strings with spaces
> 2.  Store all words in a string array.
> 3.  Now run a loop from 0 to string array length to check whether our string is equal to the word "is".
> 4.  If the condition is true, increase the count, otherwise, do not increase the count.

**代码:**

## C#

```cs
// C# program to count the number
// of occurrence of a "is" in
// the given string
using System;

class GFG{

static int countOccurrencesOfIs(string str)
{

    // Split the string by spaces
    string[] a = str.Split(' ');
    string word = "is";

    // Search for "is" in string
    int count = 0;
    for(int i = 0; i < a.Length; i++)
    {    

        // If "is" found increase count
        if (word.Equals(a[i]))
            count++;
    }
    return count;
}

// Driver code
public static void Main()
{
    string str = "is this is the way to talk to your " + 
                 "sister? I don't know what that is";
    Console.Write(countOccurrencesOfIs(str));
}
}
```

**输出:**

```cs
3
```

**时间复杂度:** O(n)其中 n 是字符串的长度。