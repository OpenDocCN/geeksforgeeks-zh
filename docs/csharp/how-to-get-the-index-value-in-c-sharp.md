# 如何在 C# 中获取索引值？

> 原文:[https://www . geeksforgeeks . org/如何获取 c-sharp 中的索引值/](https://www.geeksforgeeks.org/how-to-get-the-index-value-in-c-sharp/)

在 C# 8.0 中引入了[索引结构](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)。它表示可用于索引集合或序列的类型，并且可以从开始或结束开始。您可以借助索引结构提供的**值属性**获得索引值。

**语法:**

```cs
public int Value { int get(); };
```

**例 1:**

```cs
// C# program to illustrate the 
// concept of the value property
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
        var val4 = new Index(3, false);

        // Getting the value of the index
        var res1 = val1.Value;
        var res2 = val2.Value;
        var res3 = val3.Value;
        var res4 = val4.Value;

        // Display index value
        Console.WriteLine("Index value is : " + res1);
        Console.WriteLine("Index value is : " + res2);
        Console.WriteLine("Index value is : " + res3);
        Console.WriteLine("Index value is : " + res4);
    }
}
}
```

**输出:**

```cs
Index value is : 1
Index value is : 2
Index value is : 1
Index value is : 3

```

**例 2:**

```cs
// C# program to illustrate the 
// concept of the value property
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        string[] greetings = new string[] {"Hello", "Hola", "Namaste", 
                               "Bonjour", "Ohayo", "Ahnyounghaseyo"};

        // Creating index
        // Using Index() constructor
        var val1 = new Index(1, true);
        var val2 = new Index(2, false);

        // Checking the given both the 
        // index values are equal or not
        if (val1.Value.Equals(val2.Value) == true) 
        {
            Console.WriteLine("Both the indexes are equal and"+
              " their elements are : {0}, {1}", greetings[val1],
                                              greetings[val2]);
        }

        else {
            Console.WriteLine("Both the indexes are not equal"+
           " and their elements are : {0}, {1}", greetings[val1],
                                               greetings[val2]);
        }
    }
}
}
```

**输出:**

```cs
Both the indexes are not equal and their elements are : Ahnyounghaseyo, Namaste
```