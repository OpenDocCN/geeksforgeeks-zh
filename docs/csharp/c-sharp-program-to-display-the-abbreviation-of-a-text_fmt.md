# 显示文本缩写的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-display-the-abbreviation-of-a-text/](https://www.geeksforgeeks.org/c-sharp-program-to-display-the-abbreviation-of-a-text/)

给定一个文本，我们需要显示文本的缩写。缩写是任何单词或短语的最短形式。它包含一组取自单词或短语完整形式的字母。例如，GeeksforGeeks 的缩写是 GFG，或者 Advance Data Structure 的缩写是 ADS。

## 示例

```cs
Input : Geeks For Geeks
Output: G.F.G

Input : Data Structures Algorithms
Output: D.S.A
```

## 方法

要打印文本的缩写，请按照以下步骤操作：

*   初始化一个空字符串（`abbreviation`）。
*   将字符串的第一个字母作为缩写附加，并附加一个 `.` 到缩写中，如下所示。
*   现在，如果遇到空格、制表符或换行符，字符串将从左到右迭代，然后下一个字母将被附加到缩写中，同时附加一个 `.` 到缩写中。
*   迭代结束时，缩写将包含给定字符串的缩写。

## C# 示例

```cs
// C# program to print the abbreviation of a Text
using System;

class GFG{

public static string Abbreviation(string inputstr)
{
    string abbr = "";
    int i = 0;
    abbr += inputstr[0];
    abbr += '.';

for(i = 0; i < inputstr.Length - 1; i++)
    {
        if (inputstr[i] == ' ' || inputstr[i] == '\t' || 
            inputstr[i] == '\n')
        {
            abbr += inputstr[i + 1];
            abbr += '.';
        }
    }
    return abbr;
}

// Driver code
public static void Main()
{
    string str = "Geeks For Geeks";
    string abr = "";

abr = Abbreviation(str);

Console.Write("The Abbreviation : " + abr);
}
}
```

## 输出

```cs
The Abbreviation : G.F.G.
```

## 解释

在这个例子中，我们创建了一个 `Abbreviation()` 方法，返回指定字符串的缩写。或者我们可以说它返回一个包含单词首字母的字符串，如果单词前有空格、制表符或换行符，则该字符串会被添加到缩写字符串中，同时还会有一个 `.`。就像在字符串“Geeks For Geeks”中，缩写是 G.F.G。