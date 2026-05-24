# c# 中只读

> 原文:[https://www.geeksforgeeks.org/readonly-in-c-sharp/](https://www.geeksforgeeks.org/readonly-in-c-sharp/)

在 C# 中，readonly 关键字是一个修饰符，其使用方式如下:

**1。只读字段:**在 C# 中，允许使用只读修饰符声明字段。它表示对字段的赋值只是声明的一部分，或者在同一类的构造函数中。这类字段只能在声明或构造函数中多次赋值或重新分配。它们不会在构造函数退出后被赋值。如果 readonly 修饰符与值类型字段一起使用，则该字段是不可变的。如果 readonly 修饰符与引用类型字段一起使用，那么 readonly 修饰符防止该字段被引用类型的不同实例替换，这里 readonly 修饰符并不阻止通过只读字段修改该字段的实例数据。在静态和实例构造函数中，允许将只读字段作为 out 或 ref 参数传递。

**示例:**

```cs
// C# program to illustrate
// how to create a readonly field
using System;

class GFG {

    // readonly variables
    public readonly string str1;
    public readonly string str2;

    // Readonly variable
    // This variable is 
    // initialized at declaration time
    public readonly string str3 = "gfg";

    // The values of the readonly
    // variables are assigned
    // Using constructor
    public GFG(string a, string b)
    {

        str1 = a;
        str2 = b;
        Console.WriteLine("Display value of string 1 {0}, "
                         + "and string 2 {1}", str1, str2);
    }

    // Main method
    static public void Main()
    {
        GFG ob = new GFG("GeeksforGeeks", "GFG");
    }
}
```

**输出:**

```cs
Display value of string 1 GeeksforGeeks, and string 2 GFG
```

这里，str1 和 str2 的值在构造函数中赋值。

**2。只读结构:**在只读结构中，Readonly 修饰符表示给定的结构是不可变的。当您创建只读结构时，有必要对其字段使用只读修饰符，如果您不这样做，那么编译器将给出一个错误。

**示例:**

```cs
// C# program to illustrate how 
// to create a readonly structure
using System;

// Readonly structure
public readonly struct Author
{

    public readonly string Name { get; }
    public readonly int Article { get; }
    public readonly string Branch { get; }
    public Author(string name, int article, string branch)
    {

        this.Name = name;
        this.Article = article;
        this.Branch = branch;
    }
}

class GFG {

    // Main method
    static public void Main()
    {
        Author a = new Author("Rohit", 67, "CSE");
        Console.WriteLine("Author name: " + a.Name);
        Console.WriteLine("Total articles: " + a.Article);
        Console.WriteLine("Branch name: " + a.Branch);
    }
}
```

**输出:**

```cs
Author name: Rohit
Total articles: 67
Branch name: CSE

```

**3。只读成员:**这个特性在 C# 8.0 中引入。在此功能中，您可以对结构的任何成员使用只读修饰符。此 readonly 修饰符指定成员不允许修改。这比只读应用整个结构要好。

**示例:**

```cs
// C# program to illustrate how 
// to create a readonly member
using System;

public struct Customer
{

    public string Name { get; }
    public int Price { get; }

    // Readonly member
    public readonly string Product { get; }

    public Customer(string name, string product, int price)
    {

        this.Name = name;
        this.Product = product;
        this.Price = price;
    }
}

class GFG {

    // Main method
    static public void Main()
    {
        Customer a = new Customer("Sumit", "Mobile Phone", 2398);
        Console.WriteLine("Customer name: " + a.Name);
        Console.WriteLine("Product: " + a.Product);
        Console.WriteLine("Price: " + a.Price);
    }
}
```

**输出:**

```cs
Customer name: Sumit
Product: Mobile Phone
Price: 2398

```