# c#–查找字符串中所有子字符串的不同方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-differential-way-find-all-substrings-in-a-string/](https://www.geeksforgeeks.org/c-sharp-different-ways-to-find-all-substrings-in-a-string/)

给定一个字符串作为输入，我们需要找到给定字符串中存在的所有子字符串。

**示例:**

```cs
Input:
geeks
Output:
g
e
e
k
s
ge
ee
ek
ks
gee
eek
eks
geek
eeks
geeks

Input:
ab
Output:
a
b
ab
```

**方法 1:使用 Substring()方法**

我们可以使用 [Substring()](https://www.geeksforgeeks.org/c-sharp-substring-method/) 方法从给定的字符串中找到所有的子字符串。此方法返回当前字符串的子字符串。它包含两个参数，其中第一个参数表示必须检索的子串的起始位置和，第二个参数表示子串的长度。这里，如果第一个参数等于字符串的长度，那么这个方法将不返回任何内容。

**语法:**

> str.substring(线条索引，射线)

其中 strindex 是子字符串的起始索引，strlen 是子字符串的长度。

**接近**

显示

*   从用户处读取字符串。
*   编写 find_substrings()函数来获取子字符串。
*   在 find_substrings()函数中，调用 Substring()方法获取子字符串。

```cs
for(i = 1; i <= input_string.Length; i++)
{
    for (j = 0; j <= input_string.Length - i; j++)
    {  
        // Use Substring function
        Console.WriteLine(input_string.Substring(j, i));
    }
}
```

*   现在显示检索到的子字符串。

**示例:**

## C#

```cs
// C# program to display all Substrings
// present in the given String 
using System;

class GFG{

// Function to get the substrings
static void find_substrings(string input_string)
{
    int j = 0;
    int i = 0;

    for(i = 1; i <= input_string.Length; i++)
    {
        for(j = 0; j <= input_string.Length - i; j++)
        {  

            // Using Substring() function
            Console.WriteLine(input_string.Substring(j, i));
        }
    }
}

// Driver code
public static void Main()
{

    // Declare the main string
    string input_string;

    Console.Write("Enter String : ");
    Console.Write("\n");

    // Read the string
    input_string = Console.ReadLine();

    // Call the function
    find_substrings(input_string);
}
}
```

**输出:**

```cs
Enter String :
GFG
G
F
G
GF
FG
GFG
```

**方法 2:用于循环**

我们还可以使用嵌套 for 循环从给定的字符串中找到子字符串。这里外 for 循环用于选择起始字符，中 for 循环用于将所选起始字符右侧的所有字符视为子串、的结束字符，内 for 循环用于打印从起点到终点的字符。

**示例:**

## C#

```cs
// C# program to display all Substrings
// present in the given String 
using System;

class GFG{

// Function to print all substrings
// from the given string
static void find_Substring(string inputstr, int n)
{

    // Choose starting point
    for(int l = 1; l <= n; l++)
    {

        // Choose ending point
        for(int i = 0; i <= n - l; i++)
        {

            // Display the substrings
            int q = i + l - 1;

            for(int j = i; j <= q; j++)
                Console.Write(inputstr[j]);

            Console.WriteLine();
        }
    }
}

// Driver code
static public void Main ()
{
    string inputstr = "Geeks";

    // Calling function
    find_Substring(inputstr, inputstr.Length);
}
}
```

**输出:**

```cs
G
e
e
k
s
Ge
ee
ek
ks
Gee
eek
eks
Geek
eeks
Geeks
```