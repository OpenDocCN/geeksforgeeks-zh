# 获取 C# 中给定索引的哈希码

> 原文:[https://www . geeksforgeeks . org/get-c-sharp 中给定索引的哈希代码/](https://www.geeksforgeeks.org/getting-the-hash-code-of-the-given-index-in-c-sharp/)

在 C# 8.0 中引入了[索引结构](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)。它表示可用于索引集合或序列的类型，并且可以从开始或结束开始。您可以借助索引结构提供的**获取哈希码方法**找到指定索引的哈希码。此方法返回指定索引的哈希代码。

**语法:**

```cs
public override int GetHashCode();
```

**例 1:**

```cs
// C# program to illustrate the 
// concept of the GetHashCode() method
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

        // Getting the hash code
        // of the given index
        // Using GetHashCode() method
        var res1 = in1.GetHashCode();
        var res2 = in2.GetHashCode();

        // Displaying the index
        Console.WriteLine("Hash Code of Index: {0} is: {1} ", in1, res1);
        Console.WriteLine("Hash Code of Index: {0} is: {1} ", in2, res2);
    }
}
}
```

**输出:**

```cs
Hash Code of Index: ^1 is: -2 
Hash Code of Index: 3 is: 3 

```

**例 2:**

```cs
// C# program to illustrate the concept
// of the GetHashCode() method
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Creating and initializing an array
        string[] greetings = new string[] {"Hello", "Hola", "Namaste", 
                                "Bonjour", "Ohayo", "Ahnyounghaseyo"};

        // Creating new indexes
        // Using Index() constructor
        var in1 = new Index(2, true);
        var in2 = new Index(3, false);
        var in3 = new Index(2, false);

        // Getting the hash code
        // of the given indexes
        // Using GetHashCode() method
        var res1 = greetings[in1].GetHashCode();
        var res2 = greetings[in2].GetHashCode();
        var res3 = greetings[in3].GetHashCode();

        // Displaying the index
        Console.WriteLine("Index: {0} Value: {1} HashCode: {2} ",
                                     in1, greetings[in1], res1);

        Console.WriteLine("Index: {0} Value: {1} HashCode: {2} ",
                                     in2, greetings[in2], res2);

        Console.WriteLine("Index: {0} Value: {1} HashCode: {2} ",
                                     in3, greetings[in3], res3);
    }
}
}
```

**输出:**

```cs
Index: ^2 Value: Ohayo HashCode: -1302855152 
Index: 3 Value: Bonjour HashCode: 399419679 
Index: 2 Value: Namaste HashCode: 1350085290 

```