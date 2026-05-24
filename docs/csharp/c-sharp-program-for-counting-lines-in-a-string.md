# 计算字符串行数的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-for-program-counting-in-line-in-a-string/](https://www.geeksforgeeks.org/c-sharp-program-for-counting-lines-in-a-string/)

在 C# 中，[字符串](https://www.geeksforgeeks.org/c-sharp-string/)是 Unicode 字符序列或字符数组。Unicode 字符的范围是从 U+0000 到 U+FFFF。字符串是文本的表示形式。在本文中，我们将创建一个 C# 程序来计算给定字符串中的行数。

**示例:**

```cs
Input  : hey geeks\n welcome to \n geeksforgeeks \n happy learning
Output : 4

Input  : welcome\n to geeksforgeeks
Output : 2
```

因此，我们可以使用以下方法来完成这项任务:

*   通过计算换行符
*   使用 Split()方法
*   通过使用 Regex。匹配方法
*   通过使用 IndexOf()方法

### 方法 1:计算换行符

给定一个有多行的字符串，我们需要找到字符串中存在的行数。正如我们所知，字符串中的行由换行符(即\n)分隔。因此，我们使用以下方法来计算字符串中的行数。

**进场:**

> *   Initialize the variable count to zero.
> *   Iterate the given string using a for loop.
> *   If a new line character (\n) is encountered, increase the value of count by 1.
> *   At the end of the iteration, the count variable will be the value of the number of rows in the given string.

**示例:**

在本例中，在“inputstr”变量中赋值的整个字符串将从左向右迭代。如果遇到换行符，则表示新的一行开始，因此我们将行数增加 1。最后将得到字符串中的行数。

## C#

```cs
// C# program to display the total number of lines
// present in the given string
using System;

class GFG{

static void Main()
{

    // Initializing a string with multiple lines.
    string intputstr = "hey geeks\n welcome to \n " +
                       "geeksforgeeks \n happy learning ";
    int count = 1;

    Console.WriteLine("Input String:\n" + intputstr);

    // Iterating the string from left to right
    for(int i = 0; i < intputstr.Length; i++)
    {

        // Checking if the character encountered is
        // a newline character if yes then increment
        // the value of count variable
        if (intputstr[i] == '\n')
            count++;
    }

    // Print the count
    Console.Write("\nNumber of new lines:" + count);
}
}
```

**输出:**

```cs
Input String:
hey geeks
welcome to
geeksforgeeks
happy learning

Number of new lines:4
```

### 方法 2:使用 Split()方法

[Split()](https://www.geeksforgeeks.org/string-split-method-in-c-sharp-with-examples/) 方法返回一个字符串数组，该数组是通过拆分由作为参数在 Split()方法中传递的分隔符分隔的字符串而生成的。这里，我们将\n 作为参数传递给 Split()方法，该方法将行分割成字符串，并形成一个行数组。现在找到给出字符串中行数的数组的长度。

**语法:**

> 字符串。拆分(' \n ')。长度

**示例:**

在本例中，在“inputstr”变量中指定的给定字符串被拆分成一个字符串数组，在每个有换行符的位置进行拆分。现在数组的长度是字符串中出现的换行符的数量。

## C#

```cs
// C# program to display the total number of lines
// present in the given string. Using Split() method
using System;

class GFG{

static void Main()
{
    // Initializing a string with multiple lines.
    string intputstr = "hey geeks\n welcome to \n " +
                       "geeksforgeeks \n happy learning ";

    Console.WriteLine("Input String:\n" + intputstr);

    // Now the Split('\n') method splits the newline
    // characters and returns an array of strings and
    // the Length is used to find the length of the array.
    int result = intputstr.Split('\n').Length;

    // Print the count
    Console.Write("\nNumber of new lines:" + result);
}
}
```

**输出:**

```cs
Input String:
hey geeks
welcome to
geeksforgeeks
happy learning

Number of new lines:4
```

### 方法 3:使用正则表达式。匹配()方法

我们还可以使用 Regex 计算给定字符串中的行数。匹配()方法。这用于在指定的输入字符串中搜索给定正则表达式的所有匹配项。

**语法:**

> Regex。匹配(字符串输入，字符串匹配模式)

在这里，这个方法使用两个名为“inputstr”的参数来搜索匹配的输入字符串，并使用“matchpattern”来表示与 input tr 匹配的正则表达式模式。

**示例:**

在这个例子中，我们将在 Matches()方法中传递一个正则表达式**“**\ n”，并找到它的出现次数，通过添加一个 1，我们将得到字符串中的行数。

## C#

```cs
// C# program to count the lines in the given string
// Using Regular Expressions
using System;
using System.Text.RegularExpressions;
class GFG{

static void Main()
{

    // Input string
    string inputstr = "hey geeks\n welcome to \n " +
                       "geeksforgeeks \n happy learning ";

    Console.WriteLine("Input string:" + inputstr);

    // Passing string and regular expression to the
    // matches method we are adding 1 to number of
    // occurrences of \n because we will not have
    // \n at the end of last line
    int result = Regex.Matches(inputstr, "\n").Count + 1;
    Console.Write("Total number of lines: " + result);
}
}
```

**输出:**

```cs
Input string:hey geeks
welcome to
geeksforgeeks
happy learning
Total number of lines: 4
```

### 方法 4:使用 IndexOf()方法

我们也可以使用 [IndexOf()](https://www.geeksforgeeks.org/c-sharp-string-indexof-method-set-1/) 方法计算给定字符串中的行数。此方法用于查找给定字符串中给定字符的第一个匹配项的从零开始的索引。在此方法中，指定字符的搜索从指定位置开始，如果找不到该字符，它将返回-1。

**语法:**

> public int IndexOf(char y，int startchar)

此方法采用两个参数第一个参数是 char y，它表示要搜索的字符，第二个参数是 startchar，以整数值的形式表示开始搜索的位置。

**示例:**

在本例中，while 循环计算“inputstr”中出现的换行符总数。在这个 while 循环中，我们使用 IndexOf()方法，其中我们传递“inputstr”和“\n”，然后我们检查序列的索引是否等于 true，如果指定条件的值为 true，则执行指定的语句并显示输出。

## C++

```cs
// C# program to count the lines in the given string
// Using Regular Expressions
using System;
using System.Text.RegularExpressions;
class GFG{

static void Main()
{

    // Input string
    string inputstr = "hey geeks\n welcome to \n " +
                       "geeksforgeeks \n happy learning ";

    // Display the input string
    Console.WriteLine("Input string:" + inputstr);

    int countlines = 1;
    int startingpoint = 0;

    // Here the while loop counts the number
    // of lines present in the given string
    // Using IndexOf() method.
    while ((startingpoint = inputstr.IndexOf(
            '\n', startingpoint)) != -1)
    {
        countlines++;
        startingpoint++;
    }

    Console.Write("Total number of lines: " + countlines);
}
}
```

**输出:**

```cs
Input string:hey geeks
welcome to
geeksforgeeks
happy learning
Total number of lines: 4
```