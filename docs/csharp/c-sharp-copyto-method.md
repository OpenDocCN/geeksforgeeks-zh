# C# | CopyTo()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-copyto-method/](https://www.geeksforgeeks.org/c-sharp-copyto-method/)

在 [**C#**](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 中，CopyTo()方法是一个字符串方法。它用于从字符串中的指定位置复制指定数量的字符，并将该字符串的字符复制到 Unicode 字符数组中。

**语法:**

```cs
public void CopyTo(int sourceIndex, char[] destination, 
                      int destinationIndex, int count)

```

**说明:** CopyTo()方法将计数字符从源索引位置复制到目标字符数组的目标索引位置。该方法接受**四个参数**如下:

1.  **源索引:**要复制的字符串的索引。其类型是**系统。Int32** 。
2.  **目的地:**是要复制字符的 Unicode 字符数组。它的类型是**系统。Char[]** 。
3.  **目标索引:**是从复制操作开始的数组的起始索引。它的类型是**系统。Int32** 。
4.  **计数:**是复制到目的地的字符数。它的类型是**系统。Int32** 。

**示例:**

```cs
Input : str  = "GeeksForGeeks"
        char [] Copystring = new char[15];     
        str.CopyTo(5, Copystring, 0, 3);
Output: For

Input : str2 = "GeeksForGeeks";
        char [] Copystring = {'H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd'};
        str2.CopyTo(8, Copystring, 6, 5);
Output: Hello Geeks

```

下面的示例程序说明了 ToCopy()方法:

*   **例 1:**

    ```cs
    // C# program to illustrate the
    // ToCopy() string method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {
            string str = "GeeksForGeeks";
            char[] dest = new char[15];

            // str index 5 to 5+3 has to 
            // copy into Copystring
            // 3 is no. of character
            // 0 is start index of Copystring
            str.CopyTo(5, dest, 0, 3);

            // Displaying String
            Console.Write("The Copied String in dest Variable is: ");
            Console.WriteLine(dest);
        }
    }
    ```

    **输出:**

    ```cs
    The Copied String in dest Variable is: For

    ```

*   **例 2:**

    ```cs
    // C# program to illustrate the
    // ToCopy() string method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {
            string str2 = "GeeksForGeeks";
            char[] dest = {'H', 'e', 'l', 'l', 'o', ' ',
                                 'W', 'o', 'r', 'l', 'd' };

            // str index 8 to 8 + 5 has 
            // to copy into Copystring
            // 5 is no of character
            // 6 is start index of Copystring
            str2.CopyTo(8, dest, 6, 5);

            // Displaying the result
            Console.Write("String Copied in dest is: ");
            Console.WriteLine(dest);
        }
    }
    ```

    **输出:**

    ```cs
    String Copied in dest is: Hello Geeks

    ```

**注意:**如果“目的地”为空，那么它将导致异常，如**参数空异常**。异常发生时有不同的情况:**argumentout of range exception**

> **情况 1:** 如果 sourceIndex、destinationIndex 或 count 为负数。
> **情况 2:** 如果 sourceIndex 没有标识当前实例中的位置。
> **情况 3:** 如果 destinationIndex 没有在目标数组中标识有效的索引。
> **情况 4:** 如果计数大于子串从 startIndex 到这个实例结束的长度
> **情况 5:** 如果计数大于子串从 destinationIndex 到目的数组结束的长度。

**参考:**T2