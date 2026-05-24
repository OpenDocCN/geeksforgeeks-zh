# C# |对象。GetHashCode()方法示例

> 原文:[https://www . geesforgeks . org/c-sharp-object-gethashcode-method-with-examples/](https://www.geeksforgeeks.org/c-sharp-object-gethashcode-method-with-examples/)

此方法用于返回此实例的哈希代码。哈希代码是一个数值，用于在基于哈希的集合中插入和标识对象。`GetHashCode` 方法为需要快速检查对象相等性的算法提供了这个哈希代码。

**语法:**

```cs
public virtual int GetHashCode ();
```

**返回值:**该方法返回当前对象的 32 位有符号整数哈希码。

以下程序说明了**对象的使用。GetHashCode()** 方法:

**例 1:**

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

**例 2:**

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

**重要提示:**

*   Two objects that return different hash codes indicate that the objects are not equal, otherwise they are not valid. It means that equal hash codes do not mean that objects are equal, because different (unequal) objects can have the same hash codes.
*   [。 The. net framework](https://www.geeksforgeeks.org/introduction-to-net-framework/) does not guarantee the default implementation of the GetHashCode method, and the value returned by this method may be different between [. NET Framework](https://www.geeksforgeeks.org/introduction-to-net-framework/) versions and platforms, such as 32-bit and 64-bit platforms.
*   Hash code is not a permanent value, so don't serialize it. Store the hash value in a database, etc.
*   Don't judge whether two objects are equal by testing whether hash codes are equal.

**参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . object . gethashcode？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.object.gethashcode?view=netframework-4.7.2)