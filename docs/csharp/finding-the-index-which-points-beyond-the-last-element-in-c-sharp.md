# 找到指向 C# 中最后一个元素之外的索引

> 原文:[https://www . geeksforgeeks . org/find-the-index-指向 c-sharp 中最后一个元素之外的内容/](https://www.geeksforgeeks.org/finding-the-index-which-points-beyond-the-last-element-in-c-sharp/)

在 C# 8.0 中引入了[索引结构](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)。它表示可用于索引集合或序列的类型，并且可以从开始或结束开始。您可以在索引结构提供的**结束属性**的帮助下找到索引，该索引指向指定集合的最后一个元素之外。

**语法:**

```cs
public static property Index End { Index get(); };
```

**例 1:**

```cs
// C# program to illustrate how 
// to get the End index
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

        // Getting the end index
        var res1 = Index.End;

        // Displaying the index
        Console.WriteLine("Index: {0}", in1);
        Console.WriteLine("Index: {0}", in2);
        Console.WriteLine("End Index: {0}", res1);
    }
}
}
```

**输出:**

```cs
Index: ^1
Index: 3
End Index: ^0

```

**例 2:**

```cs
// C# program to illustrate the
// concept of the End index
using System;

namespace example {

class GFG {

     // Main Method
    static void Main(string[] args)
    {
        string[] greetings = new string[] {"Hello", "Hola", "Namaste",
                                "Bonjour", "Ohayo", "Ahnyounghaseyo"};

        // Get the end index
        var res = Index.End;

        // Checking the given index
        // is the end index or not
        if (res.Equals (^0) == true) {

            Console.WriteLine("The given index is "+
                        "beyond the last element");
        }

        else {

            Console.WriteLine("The given index is not"+
                          " beyond the last element");
        }
    }
}
}
```

**输出:**

```cs
The given index is beyond the last element
```