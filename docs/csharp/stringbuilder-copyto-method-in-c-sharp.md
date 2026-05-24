# StringBuilder。C# 中的复制方法

> 原文:[https://www . geeksforgeeks . org/stringbuilder-copy to-method-in-c-sharp/](https://www.geeksforgeeks.org/stringbuilder-copyto-method-in-c-sharp/)

此方法用于将字符从该实例的指定段复制到目标字符数组的指定段。

**语法:**

> public see copy to(int source index、char[] destination、int destinationIndex、int count)；

**参数:**

*   **源索引**:这是这个实例中复制字符的起始位置。索引从零开始。
*   **目的地**:是复制字符的数组。
*   **目的地索引**:目的地中复制字符的起始位置。索引从零开始。
*   **计数**:是需要复制的字符数。

**异常:**

*   **参数空异常**:如果*目的地*为空。
*   **ArgumentOutOfRangeException**:如果*源索引*、*目的索引*或*计数*小于零或源索引大于此实例的长度。
*   **参数异常**:如果*源索引+计数*大于此实例的长度或者*目的地索引+计数*大于*目的地*的长度。

**例 1:**

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

**例 2:**

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

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . text . stringbuilder . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.copyto?view=netframework-4.7.2)