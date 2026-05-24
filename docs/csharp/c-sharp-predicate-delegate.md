# C# |谓词委托

> 原文:[https://www.geeksforgeeks.org/c-sharp-predicate-delegate/](https://www.geeksforgeeks.org/c-sharp-predicate-delegate/)

谓词委托是内置的泛型类型 [**委托**](https://www.geeksforgeeks.org/c-sharp-delegates/) 。该委托在*系统*命名空间下定义。它与那些包含一些标准集的方法一起工作，并确定传递的参数是否满足给定的标准。此委托只接受一个输入，并以 true 或 false 的形式返回值。现在，首先，我们来看看自定义委托在这种情况下是如何工作的。如下例所示。

**语法:**

```cs
public delegate bool Predicate <in P>(P obj);
```

这里，P 是对象的类型， *obj* 是要与谓词委托所代表的方法中定义的标准进行比较的对象。

**例:**

```cs
// C# program to illustrate delegates
using System;

class GFG {

    // Declaring the delegate
    public delegate bool my_delegate(string mystring);

    // Method
    public static bool myfun(string mystring)
    {
        if (mystring.Length < 7) 
        {
            return true;
        }

        else
        {
            return false;
        }
    }

    // Main method
    static public void Main()
    {

        // Creating object of my_delegate
        my_delegate obj = myfun;
        Console.WriteLine(obj("Hello"));
    }
}
```

**输出:**

```cs
True

```