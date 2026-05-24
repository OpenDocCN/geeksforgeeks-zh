# 在 C# 中的指定索引位置从集合的末尾创建索引

> 原文:[https://www . geeksforgeeks . org/从指定索引位置的集合末尾创建索引/](https://www.geeksforgeeks.org/creating-an-index-from-the-end-of-a-collection-at-a-specified-index-position-in-c-sharp/)

在 C# 8.0 中引入了[索引结构](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)。它表示可用于索引集合或序列的类型，并且可以从开始或结束开始。您可以在索引结构提供的 **FromEnd(Int32)方法**的帮助下创建结束索引。此方法返回给定集合或序列末尾指定位置的索引。

**语法:**

```cs
public static Index FromEnd(int value);
```

**例:1**

```cs
// C# program to illustrate the 
// concept of the FromEnd() Method
using System;

namespace example {

class Program {

    // Main Method
    static void Main(string[] args)
    {
        // Creating end index
        // Using FromEnd() method
        var in1 = Index.FromEnd(2);
        var in2 = Index.FromEnd(1);
        var in3 = Index.FromEnd(0);
        var in4 = Index.FromEnd(6);

        // Display index value
        Console.WriteLine("Index position is : {0} ", in1);
        Console.WriteLine("Index position is : {0} ", in2);
        Console.WriteLine("Index position is : {0} ", in3);
        Console.WriteLine("Index position is : {0} ", in4);
    }
}
}
```

**输出:**

```cs
Index position is : ^2 
Index position is : ^1 
Index position is : ^0 
Index position is : ^6

```

**例 2:**

```cs
// C# program to illustrate the
// concept of the FromEnd() method
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        string[] greetings = new string[] {"Hello", "Hola", "Namaste", 
                                "Bonjour", "Ohayo", "Ahnyounghaseyo"};

        // Creating end index
        // Using FromEnd() method
        var index_1 = Index.FromEnd(3);
        var index_2 = Index.FromEnd(1);
        var index_3 = Index.FromEnd(4);
        var index_4 = Index.FromEnd(5);

        // Displaying index and their values
        Console.WriteLine("Index: {0} Value: {1}", 
                     index_1, greetings[index_1]);

        Console.WriteLine("Index: {0} Value: {1}", 
                     index_2, greetings[index_2]);

        Console.WriteLine("Index: {0} Value: {1}", 
                     index_3, greetings[index_3]);

        Console.WriteLine("Index: {0} Value: {1}",
                     index_4, greetings[index_4]);
    }
}
}
```

**输出:**

```cs
Index: ^3 Value: Bonjour
Index: ^1 Value: Ahnyounghaseyo
Index: ^4 Value: Namaste
Index: ^5 Value: Hola

```