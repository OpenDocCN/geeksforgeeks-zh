# StringBuilder：C# 中的 CopyTo 方法

> 原文：[https://www.geeksforgeeks.org/stringbuilder-copyto-method-in-c-sharp/](https://www.geeksforgeeks.org/stringbuilder-copyto-method-in-c-sharp/)

此方法用于将字符从该实例的指定段复制到目标字符数组的指定段。

## 语法

`public void CopyTo(int sourceIndex, char[] destination, int destinationIndex, int count);`

## 参数

*   `sourceIndex`：这是这个实例中复制字符的起始位置。索引从零开始。
*   `destination`：是复制字符的数组。
*   `destinationIndex`：目的地中复制字符的起始位置。索引从零开始。
*   `count`：是需要复制的字符数。

## 异常

*   `ArgumentNullException`：如果 `destination` 为空。
*   `ArgumentOutOfRangeException`：如果 `sourceIndex`、`destinationIndex` 或 `count` 小于零，或 `sourceIndex` 大于此实例的长度。
*   `ArgumentException`：如果 `sourceIndex + count` 大于此实例的长度，或者 `destinationIndex + count` 大于 `destination` 的长度。

## 例 1

```cs
// C# program to illustrate the
// CopyTo () StringBuilder Method
using System;
using System.Text;

class Geeks {

// Main Method
    public static void Main()
    {
        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("GeeksForGeeks");

        char[] dest = new char[15];

        // str index 5 to 5+3 has to
        // copy into Copystring
        // 3 is no. of character
        // 0 is start index of Copystring
        str.CopyTo(5, dest, 0, 3);

        // Displaying String
        Console.Write("The Copied String in "+
                        "dest Variable is: ");
        Console.WriteLine(dest);
    }
}
```

**Output:**

```cs
The Copied String in dest Variable is: For
```

## 例 2

```cs
// C# program to illustrate the
// CopyTo() StringBuilder Method
using System;
using System.Text;

class Geeks {

// Main Method
    public static void Main()
    {
        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str2
            = new StringBuilder("GeeksForGeeks");

        char[] dest = { 'H', 'e', 'l', 'l', 'o', ' ',
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

**Output:**

```cs
String Copied in dest is: Hello Geeks
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.copyto?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.copyto?view=netframework-4.7.2)