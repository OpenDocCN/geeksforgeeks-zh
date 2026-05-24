# C# Object.GetHashCode() 方法详解与示例

> 原文：[https://www.geeksforgeeks.org/c-sharp-object-gethashcode-method-with-examples/](https://www.geeksforgeeks.org/c-sharp-object-gethashcode-method-with-examples/)

此方法用于返回此实例的哈希代码。哈希代码是一个数值，用于在基于哈希的集合中插入和标识对象。`GetHashCode` 方法为需要快速检查对象相等性的算法提供了这个哈希代码。

## 语法

```cs
public virtual int GetHashCode ();
```

## 返回值

该方法返回当前对象的 32 位有符号整数哈希码。

以下程序说明了 `Object.GetHashCode()` 方法的使用：

### 示例1

```cs
// C# program to demonstrate
// Object.GetHashCode() Method
using System;

class GFG {

// Main Method
    public static void Main()
    {

// declaring an object
        Object obj = new Object();

// taking Type type and assigning
        // the value as type of above
        // defined types using GetType
        // method
        Type t = obj.GetType();

// Display type and hash code
        Console.WriteLine("Type is :{0}", t);
        Console.WriteLine("Hash Code is :{0}",
                             t.GetHashCode());
    }
}
```

**Output:**

```cs
Type is :System.Object
Hash Code is :37162120
```

### 示例2

```cs
// C# program to demonstrate
// Object.GetHashCode() Method
using System;

public class Author {

    public string f_Name;
    public string l_Name;

    public Author(string f_Name, 
                  string l_Name)
    {
        this.f_Name = f_Name;
        this.l_Name = l_Name;
    }

    public void Show()
    {
        Console.WriteLine("first Name : " 
                           + f_Name);

        Console.WriteLine("last Name : " 
                          + l_Name);
    }
}

// Driver Class
class GFG {

// Main method
    public static void Main()
    {

// Creating and initializing 
        // the object of Author class
        Author aobj = new Author("Kirti", "Mangal");

        Console.WriteLine("Author details:");
        aobj.Show();

// Get the Hash Code of aobj object
        // Using GetHashCode() method
        Console.WriteLine("The hash code of object is: {0}",
                                aobj.GetHashCode());
    }
}
```

**输出:**

```cs
Author details:
first Name : Kirti
last Name : Mangal
The hash code of object is: -751588944
```

## 重要提示

*   两个返回不同哈希码的对象表明它们不相等，否则它们就是无效的。这意味着相等的哈希码并不意味着对象相等，因为不同（不相等）的对象可以有相同的哈希码。
*   [.NET Framework](https://www.geeksforgeeks.org/introduction-to-net-framework/) 不保证 `GetHashCode` 方法的默认实现，此方法返回的值可能因 [.NET Framework](https://www.geeksforgeeks.org/introduction-to-net-framework/) 版本和平台（例如 32 位和 64 位平台）而异。
*   哈希码不是永久值，因此不要序列化它。不要将哈希值存储在数据库等地方。
*   不要通过测试哈希码是否相等来判断两个对象是否相等。

**参考:**[https://docs.microsoft.com/en-us/dotnet/api/system.object.gethashcode?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.object.gethashcode?view=netframework-4.7.2)