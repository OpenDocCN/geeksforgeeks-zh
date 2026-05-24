# 如何在 C# 中检查索引是从开始还是结束？

> 原文:[https://www . geeksforgeeks . org/如何检查索引是从 c-sharp 中的开始还是结束/](https://www.geeksforgeeks.org/how-to-check-whether-the-index-is-from-start-or-end-in-c-sharp/)

在 C# 8.0 中引入了[索引结构](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)。它表示可用于索引集合或序列的类型，并且可以从开始或结束开始。您可以在索引结构提供的**索引属性**的帮助下，检查给定的索引是从给定集合或序列的开始还是结束。如果 IsFramend 属性返回 false，则表示索引从开始，或者如果 IsFramend 属性返回 true，则表示索引从结束。]

**语法:**

```cs
public property bool IsFromEnd { bool get(); };
```

**例 1:**

```cs
// C# program to illustrate the
// concept of the IsFromEnd property
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
        // index start from the end
        // or not
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

**例 2:**

```cs
// C# program to illustrate the
// concept of the IsFromEnd property
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        string[] greetings = new string[] {"Hello", "Hola", "Namaste", 
                                "Bonjour", "Ohayo", "Ahnyounghaseyo"};

        var val1 = new Index(1, true);

        // Checking the given index
        // is the end index or not
        if (val1.IsFromEnd == true) {
            Console.WriteLine("The given index is from end "+
                     "and the value is: " + greetings[val1]);
        }
        else {
            Console.WriteLine("The given index is from start and"+
                             " the value is: " + greetings[val1]);
        }
    }
}
}
```

**输出:**

```cs
The given index is from end and the value is: Ahnyounghaseyo
```