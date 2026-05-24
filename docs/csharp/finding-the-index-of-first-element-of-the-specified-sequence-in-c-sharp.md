# 在 C# 中找到指定序列的第一个元素的索引

> 原文:[https://www . geeksforgeeks . org/find-c-sharp 中指定序列的第一个元素的索引/](https://www.geeksforgeeks.org/finding-the-index-of-first-element-of-the-specified-sequence-in-c-sharp/)

在 C# 8.0 中引入了[索引结构](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)。它表示可用于索引集合或序列的类型，并且可以从开始或结束开始。您可以在索引结构提供的**开始属性**的帮助下找到指向指定集合或序列的第一个元素的索引。

**语法:**

```cs
public static property Index Start { Index get(); };
```

**例 1:**

```cs
// C# program to illustrate the
// concept of the start index
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Creating new indexes
        // Using Index() constructor
        var in1 = new Index(1, true);
        var in2 = new Index(3, false);

        // Get the start index
        var res1 = Index.Start;

        // Displaying the index
        Console.WriteLine("Index: {0}", in1);
        Console.WriteLine("Index: {0}", in2);
        Console.WriteLine("Start Index: {0}", res1);
    }
}
}
```

**输出:**

```cs
Index: ^1
Index: 3
Start Index: 0

```

**例 2:**

```cs
// C# program to illustrate the
// concept of the start index
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Creating and initializing an array
        string[] greetings = new string[] {"Hello", "Hola", "Namaste", 
                                "Bonjour", "Ohayo", "Ahnyounghaseyo"};

        // Get the end index
        var res = Index.Start;

        // Checking the given index 
        // is the start index or not
        if (res.Equals(0) == true) {

            Console.WriteLine("The given index is start index"+
                      " and the element is " + greetings[res]);
        }

        else {

            Console.WriteLine("The given index is not the start index ");
        }
    }
}
}
```

**输出:**

```cs
The given index is start index and the element is Hello
```