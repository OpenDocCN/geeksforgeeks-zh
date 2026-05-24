# 如何在 C# 中创建 StringBuilder

> 原文:[https://www . geeksforgeeks . org/如何创建 c-sharp 中的 stringbuilder/](https://www.geeksforgeeks.org/how-to-create-the-stringbuilder-in-c-sharp/)

StringBuilder()构造函数用于初始化 StringBuilder 类的新实例，该实例将为空，并将具有默认的初始容量。StringBuilder 用于表示可变的字符串。可变是指可以改变的字符串。所以字符串对象是不可变的，但是字符串生成器是可变的字符串类型。它不会创建当前字符串对象的新修改实例，而是在现有字符串对象中进行修改。

**语法:**

```cs
public StringBuilder ();
```

**例:**

```cs
// C# Program to illustrate how
// to create a StringBuilder
using System;
using System.Text;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // sb is the StringBuilder object
        // StringBuilder() is the constructor
        // used to initializes a new
        // instance of the StringBuilder class
        StringBuilder sb = new StringBuilder();

        // Capacity property is used to get
        // maximum number of characters that
        // can be contained in the memory
        // allocated by the current instance
        Console.WriteLine(sb.Capacity);
    }
}
```

**输出:**

```cs
16

```

这里 16 是默认容量。

**注意:**

*   Use this constructor to set the string value of the current instance to *string. Empty* .
*   Capacity is set to implement specific default capacity. This is 16.