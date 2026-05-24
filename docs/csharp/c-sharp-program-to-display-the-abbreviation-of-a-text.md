# 显示文本缩写的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-display-a-text 的缩写/](https://www.geeksforgeeks.org/c-sharp-program-to-display-the-abbreviation-of-a-text/)

给定一个文本，我们需要显示文本的缩写。缩写是任何单词或短语的最短形式。它包含一组取自单词或短语完整形式的字母。例如，GeeksforGeeks 的缩写是 GFG，或者 Advance Data Structure 的缩写是 ADS。

**例:**

```cs
Input : Geeks For Geeks
Output: G.F.G

Input : Data Structures Algorithms
Output: D.S.A
```

**方法:**

> 要打印文本的缩写，请按照以下步骤操作:
> 
> *   Initialize an empty string (abbreviation).
> *   Attach the first letter of the string as an abbreviation, and attach a **''** abbreviation as follows
> *   Now, if you encounter spaces, tabs or line breaks, the string will iterate from left to right, and then the next letter will be attached to the abbreviation with "**".** to abbreviation
> *   At the end of the iteration, the abbreviation will have the abbreviation of the given string.

**例:**

## c#

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

**输出**

```cs
The Abbreviation : G.F.G.
```

**解释:**在这个例子中，我们创建了一个缩写()方法，返回指定字符串的缩写。或者我们可以说它返回一个包含单词首字母的字符串，如果单词前有空格、制表符或换行符，则该字符串会被添加到缩写字符串中，同时还会有一个“**”。还增加了**。就像在字符串“极客”中，缩写是 G.F.G