# 在 C# 中从集合开始处的指定索引创建索引

> 原文:[https://www . geeksforgeeks . org/在 c-sharp 中的集合开始时从指定索引创建索引/](https://www.geeksforgeeks.org/creating-an-index-from-the-specified-index-at-the-start-of-a-collection-in-c-sharp/)

在 C# 8.0 中引入了[索引结构](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)。它表示可用于索引集合或序列的类型，并且可以从开始或结束开始。您可以在索引结构提供的 **FromStart(Int32)方法()**的帮助下创建一个开始索引。此方法从指定位置的给定集合或序列的开始处返回一个索引。

**语法:**

```cs
public static Index FromStart(int value);
```

**例 1:**

```cs
// C# program to illustrate the 
// concept of the FromStart() method
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating start index
        // Using FromStart() method
        var in1 = Index.FromStart(2);
        var in2 = Index.FromStart(1);
        var in3 = Index.FromStart(0);
        var in4 = Index.FromStart(6);

        // Displaying  index value
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
Index position is : 2 
Index position is : 1 
Index position is : 0 
Index position is : 6 

```

**例 2:**

```cs
// C# program to illustrate the 
// concept of the FromStart() method
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        string[] greetings = new string[] {"Hello", "Hola", "Namaste", 
                                "Bonjour", "Ohayo", "Ahnyounghaseyo"};

        // Creating start index
        // Using FromStart() method
        var index_1 = Index.FromStart(0);
        var index_2 = Index.FromStart(1);
        var index_3 = Index.FromStart(4);
        var index_4 = Index.FromStart(5);

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
Index: 0 Value: Hello
Index: 1 Value: Hola
Index: 4 Value: Ohayo
Index: 5 Value: Ahnyounghaseyo

```