# c# 中的索引构造器

> 原文:[https://www.geeksforgeeks.org/index-constructor-in-c-sharp/](https://www.geeksforgeeks.org/index-constructor-in-c-sharp/)

C# 8.0 中[索引结构](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)的**索引(Int32，布尔值)构造器**用于用指定的索引位置和显示索引是从集合或序列的开始还是结束开始的值来初始化新索引。如果从末尾创建指定的索引，则索引值 1 将指向最后一个元素，索引值 0 将指向最后一个元素之外。

**语法:**

```cs
public Index (int Value, bool FromEnd = false);
```

这里，值是索引值，它是系统值。Int32 类型。索引的值应该等于或大于零。 *FromEnd* 是布尔值，表示索引是从集合或序列的*开始*还是从*结束*开始。在 C# 8.0 或更高版本上执行的以下代码:

**例 1:**

```cs
// C# program to illustrate
// the use of Index constructor
using System;

namespace example {

class GFG {

    static void Main(string[] args)
    {
        // Creating and initializing an array
        string[] greetings = new string[] {"Hello", "Hola", "Namaste", 
                                "Bonjour", "Ohayo", "Ahnyounghaseyo"};

        // Creating new indexes
        // Using Index() constructor
        var val1 = new Index(1, true);
        var val2 = new Index(2, true);
        var val3 = new Index(3, true);
        var val4 = new Index(1, false);
        var val5 = new Index(2, false);
        var val6 = new Index(3, false);

        // Getting the values of 
        // the specified indexes
        var res1 = greetings[val1];
        var res2 = greetings[val2];
        var res3 = greetings[val3];
        var res4 = greetings[val4];
        var res5 = greetings[val5];
        var res6 = greetings[val6];

        // Display indexes and their values
        Console.WriteLine("Index:{0} Value: {1}", val1, res1);
        Console.WriteLine("Index:{0} Value: {1}", val2, res2);
        Console.WriteLine("Index:{0} Value: {1}", val3, res3);
        Console.WriteLine("Index:{0} Value: {1}", val4, res4);
        Console.WriteLine("Index:{0} Value: {1}", val5, res5);
        Console.WriteLine("Index:{0} Value: {1}", val6, res6);
    }
}
}
```

**输出:**

```cs
Index:^1 Value: Ahnyounghaseyo
Index:^2 Value: Ohayo
Index:^3 Value: Bonjour
Index:1 Value: Hola
Index:2 Value: Namaste
Index:3 Value: Bonjour

```

**例 2:**

```cs
// C# program to illustrate 
// the use of Index constructor
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Creating new indexes
        // Using Index() constructor
        var val1 = new Index(1, true);
        var val2 = new Index(2, true);
        var val3 = new Index(1, false);
        var val4 = new Index(2, false);

        // Checking if the specified 
        // index start from end or not
        var res1 = val1.IsFromEnd;
        var res2 = val2.IsFromEnd;
        var res3 = val3.IsFromEnd;
        var res4 = val4.IsFromEnd;

        // Display indexes and their values
        Console.WriteLine("Index:{0} Start from end?: {1}", val1, res1);
        Console.WriteLine("Index:{0} Start from end?: {1}", val2, res2);
        Console.WriteLine("Index:{0} Start from end?: {1}", val3, res3);
        Console.WriteLine("Index:{0} Start from end?: {1}", val4, res4);
    }
}
}
```

**输出:**

```cs
Index:^1 Start from end?: True
Index:^2 Start from end?: True
Index:1 Start from end?: False
Index:2 Start from end?: False

```