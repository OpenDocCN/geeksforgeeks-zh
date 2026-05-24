# C# |创建具有指定容量的字符串生成器

> 原文:[https://www . geesforgeks . org/c-sharp-creating-stringbuilder-having-specific-capacity/](https://www.geeksforgeeks.org/c-sharp-creating-stringbuilder-having-specified-capacity/)

**StringBuilder(Int32)构造函数**用于初始化 StringBuilder 类的一个新实例，该实例将为空，并将具有指定的初始容量。StringBuilder 用于表示可变的字符串。可变是指可以改变的字符串。所以字符串对象是不可变的，但是字符串生成器是可变的字符串类型。它不会创建当前字符串对象的新修改实例，而是在现有字符串对象中进行修改。

**语法:**

```cs
public StringBuilder (int capacity);
```

这里，*容量*是 StringBuilder 实例的起始大小。如果要存储的字符数大于指定的容量，则 StringBuilder 对象将动态分配内存来存储它们。

**异常:**如果容量小于零，这将给出 ArgumentOutOfRangeException。

**例 1:**

```cs
// C# Program to illustrate how
// to create a StringBuilder having
// specified initial capacity
using System;
using System.Text;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // sb is the StringBuilder object
        // StringBuilder(10) is the constructor
        // used to initializes a new
        // instance of the StringBuilder class
        // having 10 as capacity
        StringBuilder sb = new StringBuilder(10);

        Console.Write("Capacity of StringBuilder: ");

        // using capacity property
        Console.WriteLine(sb.Capacity);
    }
}
```

**Output:**

```cs
Capacity of StringBuilder: 10

```

**例 2:** 为*argumentout of range exception*

```cs
// C# Program to illustrate how
// to create a StringBuilder having
// specified initial capacity
using System;
using System.Text;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // sb is the StringBuilder object
        // taking capacity less than zero
        StringBuilder sb = new StringBuilder(-4);

        // using capacity property
        Console.WriteLine(sb.Capacity);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:“容量”必须大于零。
> 参数名称:容量

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . text . string builder-ctor？view = net framework-4 . 7 . 2 # System _ Text _ StringBuilder _ ctor _ System _ int 32 _](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.-ctor?view=netframework-4.7.2# System_Text_StringBuilder__ctor_System_Int32_)