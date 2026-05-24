# C# | Object.GetType() 方法示例

> 原文：[https://www.geeksforgeeks.org/c-sharp-object-gettypecode-method-with-examples/](https://www.geeksforgeeks.org/c-sharp-object-gettypecode-method-with-examples/)

此方法用于返回当前实例的类型。这里，**类型**表示类型声明，即类类型、接口类型、数组类型、值类型、枚举类型、类型参数、泛型类型定义和开放或封闭构造的泛型类型。`System.Object` 类是 .NET 框架类型系统中存在的所有类型的基类。基本上，这个方法返回代表所有 .NET 框架类型的类型对象。

.NET Framework 识别出以下五类类型：

*   [Class](https://www.geeksforgeeks.org/c-class-and-object/)，派生自 `System.Object`。
*   [Value type](https://www.geeksforgeeks.org/c-data-types-2/) 来自 `System.ValueType`。
*   [Interface](https://www.geeksforgeeks.org/c-interface/) 来自 `System.Object`，始于 .NET Framework 2.0。
*   [Enumerate](https://www.geeksforgeeks.org/c-enumeration-or-enum/)，来自 `System.Enumerate`。
*   [委托](https://www.geeksforgeeks.org/c-delegates/)，来源于 `System.MulticastDelegate`。

## 语法

```cs
public Type GetType();
```

## 返回值

此方法返回当前实例的运行时类型。

以下程序说明了 `Object.GetType()` 方法的使用：

## 例 1

```cs
// C# program to demonstrate
// Object.GetType() Method
using System;

// Base class
public class G {
}

// Derived class
public class X : G {
}

// Driver Class
class GFG {

    // Main method
    public static void Main()
    {
        // Creating and initializing objects
        X obj = new X();
        G obj1 = new G();
        Object obj2 = obj;

        // Find the type of objects
        // using GetType() method
        Console.WriteLine("The X class object type is: " 
                         + obj.GetType());

        Console.WriteLine("The G class object type is: " 
                         + obj1.GetType());

        Console.WriteLine("The obj2 object type is: " 
                         + obj2.GetType());
    }
}
```

## 输出

```cs
The X class object type is: X
The G class object type is: G
The obj2 object type is: X
```

## 例 2

```cs
// C# program to demonstrate
// Object.GetType() Method
using System;

public class Author {

    public string A_Name;
    public string P_Name;
    public int n;

    public Author(string A_Name, 
                   string P_Name, int n)
    {
        this.A_Name = A_Name;
        this.P_Name = P_Name;
        this.n = n;
    }

    public void Show()
    {
        Console.WriteLine("Author Name : " + A_Name);
        Console.WriteLine("Article Name : " + P_Name);
        Console.WriteLine("Article No : " + n);
    }

    public void type()
    {
        Console.WriteLine("Type of Author Name : " 
                         + A_Name.GetType());

        Console.WriteLine("Type of Article Name : " 
                         + P_Name.GetType());

        Console.WriteLine("Type of Article No : " 
                         + n.GetType());
    }
}

// Driver Class
class GFG {

    // Main method
    public static void Main()
    {
        // Creating and initializing
        // the object of Author class
        Author obj = new Author("Kirti", 
                    "GetType() method", 3);

        Console.WriteLine("Author details:");
        obj.Show();

        // Display the type
        obj.type();
        Console.WriteLine("Type of Author class object: " 
                         + obj.GetType());
    }
}
```

## 输出

```cs
Author details:
Author Name : Kirti
Article Name : GetType() method
Article No : 3
Type of Author Name : System.String
Type of Article Name : System.String
Type of Article No : System.Int32
Type of Author class object: Author
```

## 参考

[https://docs.microsoft.com/en-us/dotnet/api/system.object.gettype?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.object.gettype?view=netframework-4.7.2)