# C# | Remove()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-remove-method/](https://www.geeksforgeeks.org/c-sharp-remove-method/)

在 C# 中， ***Remove()*** 方法是一个 String 方法。它用于从字符串的指定位置移除所有字符。如果没有指定长度，那么它将删除指定位置之后的所有字符。通过更改传递给该方法的参数数量，可以重载该方法。

**语法:**

```cs
public string Remove(int StartIndex)  
or
public string Remove(int StartIndex, int count)  

```

**解释:**
**公共字符串 Remove(int StartIndex** )方法将采用单个参数作为起始索引，或者我们可以说指定的位置，从该位置开始从当前 string 对象中删除字符。此方法将继续移除字符，直到当前字符串对象结束。

**公共字符串 Remove(int StartIndex，int count)** 方法将采用两个参数，即第一个是指定字符串的开始位置，第二个是要删除的字符数。这两种方法的返回类型值都是**系统。弦**。

**异常:**可能出现异常**ArgumentOutOfRangeException**的两种情况如下:

*   StartIndex 或(StartIndex + count)表示可能在当前字符串对象之外的位置。
*   开始索引或计数小于零。

以下是演示上述方法的程序:

*   **示例 1:** 演示**公共字符串 Remove(int StartIndex)** 方法的程序。Remove 方法将删除指定索引中的所有字符，直到字符串结束。

    ```cs
    // C# program to illustrate the
    // public string Remove(int StartIndex)
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // define string
            String str = "GeeksForGeeks";

            Console.WriteLine("Given String : " + str);

            // delete from index 5 to end of string
            Console.WriteLine("New String1 : " + str.Remove(5));

            // delete character from index 8 to end of string
            Console.WriteLine("New String2 : " + str.Remove(8));
        }
    }
    ```

    **输出:**

    ```cs
    Given String : GeeksForGeeks
    New String1 : Geeks
    New String2 : GeeksFor

    ```

*   **示例 2:** 程序演示**公共字符串 Remove(int StartIndex，int count)** 方法。此方法将从字符串的指定索引+(count–1)中删除字符，其中 count 是要删除的字符数。

    ```cs
    // C# program to illustrate the
    // public string Remove(int StartIndex, int count)
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // original string
            String str = "GeeksForGeeks";

            Console.WriteLine("Given String : " + str);

            // delete the string from index 2 to length 4
            Console.WriteLine("New String1 : " + str.Remove(2, 4));

            // delete the string from index 5 to length 3
            Console.WriteLine("New String2 : " + str.Remove(5, 3));
        }
    }
    ```

    **输出:**

    ```cs
    Given String : GeeksForGeeks
    New String1 : GeorGeeks
    New String2 : GeeksGeeks

    ```

**需要记住的要点:**

*   上述两种方法都不会修改当前字符串对象的值。相反，它们返回一个新的修改过的字符串。
*   如果 StartIndex 等于字符串的长度，并且长度为零，则该方法不会从字符串中移除任何字符。

**参考文献:**
[https://msdn . Microsoft . com/en-us/library/system . string . remove 1](https://msdn.microsoft.com/en-us/library/9ad138yc(v=vs.110).aspx)

[https://msdn . Microsoft . com/en-us/library/system . string . remove 2](https://msdn.microsoft.com/en-us/library/d8d7z2kk(v=vs.110).aspx)