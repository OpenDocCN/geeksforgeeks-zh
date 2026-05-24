# C# | IndexOfAny()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-indexofany-method/](https://www.geeksforgeeks.org/c-sharp-indexofany-method/)

在 C# 中， ***IndexOfAny()*** 法是一种 [**串**](https://www.geeksforgeeks.org/c-string/) 法。它用于搜索字符串中出现的指定字符索引，这将是从开始索引开始的第一次出现。它以整数值形式返回索引。通过更改传递给该方法的参数数量，可以重载该方法。

*   任何方法的索引(字符[])
*   任何方法的索引(Char[]，Int32)
*   任何方法的索引(Char[]，Int32，Int32)

### 任何方法的索引(字符[])

此方法将采用单个参数，即包含一个或多个要搜索的字符的字符数组。它将从起始索引开始搜索，即默认从 0 开始搜索，如果在 *ch* 中没有找到字符，则返回-1。

**语法:**

```cs
public int IndexOfAny(char[] ch)
```

*   **Parameter:** This method will adopt a single parameter of **system type. Char []** is a character array containing one or more characters to be searched.
*   **Return value:** This method will always return the first character in the current instance, in which any character of *ch* is found. It uses a zero-based index position. The return type of this method is **system. Int32** 。
*   **Exception:** If *CH* is empty, this method can give an exception ***ArgumentNullexception***

**示例:**程序演示**公共 int IndexOfAny(char[] ch)** 方法。IndexOfAny 方法将从字符串的开始到结束搜索字符，并返回整数值作为该字符第一次出现的位置。

## C#

```cs
// C# program to illustrate the
// public int IndexOfAny(char[] ch)
using System;
class GFG {

   // Main Method
    public static void Main()
    {
        String str = "GeeksForGeeks";
        Console.WriteLine("Given String : {0}\n", str);

        // to find single character
        // to start search to match character
        // 's' will be found at 5 position
        char[] ch = { 's' };
        Console.WriteLine(str.IndexOfAny(ch) + 1);

        // to find any character
        // to start search to match characters
        char[] ch1 = { 'a', 'b', 'c', 'e', 'f' };

        // 'a', 'b', 'c', 'e', 'f' then first
        // 'e' will be found at 2 position
        Console.WriteLine(str.IndexOfAny(ch1) + 1);

        char[] ch2 = { 'a', 'b', 'c' };

        // if no character found in string
        // then return -1;
        int m = str.IndexOfAny(ch2);
        if (m > -1)
            Console.Write(m);
        else
            Console.WriteLine("Not Found");
    }
}
```

**输出:**

```cs
Given String : GeeksForGeeks

5
2
Not Found
```

### 任何方法的索引(Char[]，Int32)

此方法使用指定字符数组中任何字符的当前实例中第一个匹配项的从零开始的索引。搜索从指定的字符位置开始。

**语法:**

```cs
public int IndexOfAny(char[] ch, int startIndex)
```

*   **Parameters:** This method takes two parameters, namely ***char [] CH*** type *system. Specify char []* of the character array to be searched and ***starting index*** of the system of type *. Int32* Specifies the starting index of the search string.
*   **Return value:** This method will always return the first character in the current instance, in which any character of *ch* is found. It uses a zero-based index position. The return type of this method is **system. Int32** 。
*   **Exception:** If *ch* is empty, this method will give two exceptions, namely ***ArgumentNullexception*** If [T8】 ch 【T9] is empty, Then **argument of rangeexception** If *startindex* is greater than the string to be searched, it will be *negative* .

**示例:**程序演示**public int IndexOfAny(char[]ch，int startIndex)** 方法。IndexOfAny 方法将从字符串的开始到指定的开始索引到结尾搜索字符，并返回一个整数值作为该字符第一次出现的位置。

## C#

```cs
// C# program to illustrate the
// public int IndexOfAny(char[] ch, int startIndex)
using System;
class GFG {

    // Main Method
    public static void Main()
    {

        String str = "GeeksForGeeks";
        Console.WriteLine("Given String : {0}\n", str);

        // to find single character
        char[] ch = { 's' };
        int startIndex = 6;

        // to start search from index 6 so character
        // 's' will be found at 13 position
        Console.WriteLine(str.IndexOfAny(ch, startIndex) + 1);

        // to find any character
        char[] ch1 = {'a', 'b', 'c', 'e', 'f'};
        int startIndex1 = 4;

        // to start search from index 4 so character
        // 'e' will be match first at 10 position
        Console.WriteLine(str.IndexOfAny(ch1, startIndex1) + 1);

        char[] ch2 = { 'a', 'b', 'c', 'f' };
        int startIndex2 = 5;

        // to start search from index 5
        // so no character found
        // its case sensitive search so 'f' is not match
        int m = str.IndexOfAny(ch2, startIndex2);
        if (m > -1)
            Console.Write(m);
        else
            Console.Write("Not Found");
    }
}
```

**输出:**

```cs
Given String : GeeksForGeeks

13
10
Not Found
```

### public int index ofny(char[]ch、int startIndex、int count)

此方法使用指定字符数组中任何字符的当前实例中第一个匹配项的从零开始的索引。搜索从指定的字符位置开始，并检查指定数量的字符位置。

**语法:**

```cs
public int IndexOfAny(char[] ch, int startIndex, int count) 
```

*   **Parameters:** This method takes three parameters, namely ***char [] CH*** type *system. Specify char []* of the character array to be searched, and **starting index** of the system of type *. Int32* specifies the starting index of the character string to be searched, and ***count*** of *system type. Int32* Specify the number of character positions to check.
*   **Return value:** This method will always return the first character in the current instance, in which any character of *ch* is found. It uses a zero-based index position. The return type of this method is **system. Int32** 。
*   **Exception:** If *CH* is empty and ***Argumentout of Rangeexception*** If *startindex+count* is greater than the string to be searched or both (Startindex and coun T) are both *negative* , then this method will give two exceptions, namely ***ArgumentNullexception*** .

**示例:**程序演示**公共 int IndexOfAny( char[] ch，int startIndex，int count)** 方法。此 IndexOfAny 方法将搜索字符串中从指定索引到指定索引+(count–1)的字符，其中 count 是要检查的字符数，然后返回整数值作为该字符第一次出现的位置。

## C#

```cs
// C# program to illustrate the
// public int IndexOfAny( char[] ch,
// int startIndex, int count)
using System;
class GFG {

    // Main Method
    public static void Main()
    {

        String str = "GeeksForGeeks";
        Console.WriteLine("Given String : {0}\n", str);

        // to find single character
        char[] ch = { 's' };
        int startIndex = 6;
        int count = 4;

        // to start search from index 6
        // to 10(6+4)so character
        // 's' is not found so return -1
        int r = str.IndexOfAny(ch, startIndex, count) == -1
                ? -1 : str.IndexOfAny(ch, startIndex, count) + 1;
        Console.WriteLine(r);

        // to find any character
        char[] ch1 = {'a', 'b', 'c', 'e', 'f'};
        int startIndex1 = 3;
        int count1 = 8;

        // to start search from index 3
        // to 11(3 + 8)so character
        // 's' will be match first at 10 position
        int r1 = str.IndexOfAny(ch1, startIndex1, count1) == -1
                     ? -1 : str.IndexOfAny(ch1, startIndex1, count1) + 1;
        Console.WriteLine(r1);

        char[] ch2 = {'a', 'b', 'c', 'F'};
        int startIndex2 = 5;
        int count2 = 5;

        // to start search from index 5
        // to 10(5 + 5)so character
        // 'F' will be match first at 6 position
        int r2 = str.IndexOfAny(ch2, startIndex2, count2) == -1
                     ? -1 : str.IndexOfAny(ch2, startIndex2, count2) + 1;
        Console.WriteLine(r2);
    }
}
```

**输出:**

```cs
Given String : GeeksForGeeks

-1
10
6
```

**需要记住的要点:**

*   The search of character array elements is case sensitive.
*   Search ranges from startIndex to the end of the string.
*   If the character array element is an empty array, this method finds a match at the beginning of the string.

**参考文献:**

*   [https://msdn。微软。com/en-us/library/system 字符串。索引第 1 部分](https://msdn.microsoft.com/en-us/library/11w09h50(v=vs.110).aspx)
*   [https://msdn。微软公司。com/en-us/library(美国/库)。字符串。indexofany 2](https://msdn.microsoft.com/en-us/library/56y4ddbk(v=vs.110).aspx)
*   [https://msdn。微软公司。com/en-us/library(美国/库)。字符串。indexofany 3](https://msdn.microsoft.com/en-us/library/6wh7x3fs(v=vs.110).aspx)