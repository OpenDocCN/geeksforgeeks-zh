# 物体。用例子在 C# 中克隆方法

> 原文:[https://www . geeksforgeeks . org/object-memberwiseclone-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/object-memberwiseclone-method-in-c-sharp-with-examples/)

对象。MemberwiseClone 方法用于创建当前*对象*的浅拷贝或进行克隆。浅拷贝是对象的逐位拷贝。在这种情况下，会创建一个新对象，并且该对象具有现有对象的精确副本。基本上，此方法将当前对象的非静态字段复制到新对象。

*   If the field is of reference type, only the reference, not the referenced object, is copied. So here, the cloned object and the original object will refer to the same object.
*   If the field is a value type, a bit-by-bit copy of the field will be performed.

**语法:**

```cs
protected object MemberwiseClone ();
```

**返回:**此方法返回一个*对象*，它是现有对象的浅拷贝。

**例 1:**

```cs
// C# program to clone a object
// using MemberwiseClone() method
using System;

class GFG1 {

    public int val;

    public GFG1(int val)
    {
        this.val = val;
    }

}

class GFG2 {

    public GFG1 gg;

    public GFG2(int val)
    {
        // copy the reference of GFG1 to gg
        this.gg = new GFG1(val);   
    }

    // method for cloning
    public GFG2 Clone()
    {
        // return cloned value using
        // MemberwiseClone() method
        return ((GFG2)MemberwiseClone());

    }
}

// Driver Code
class Geek {

    // Main Method
    public static void Main()
    {
        // object of Class GFG2 with a value 3
        GFG2 g = new GFG2(3);

        // calling Clone()
        // "cc" has the reference of Clone()
        GFG2 cc = g.Clone();

        // accessing the main value
        Console.WriteLine("Value: " + g.gg.val);

        // accessing the cloned value
        Console.WriteLine("cloned value: " + cc.gg.val);

        // set a new value 
        // in variable "val"
        cc.gg.val = 6;

        // accessing the main value
        Console.WriteLine("\nValue: " + g.gg.val);

        // accessing the cloned value
        Console.WriteLine("cloned value: " + cc.gg.val);

    }
}
```

**输出:**

```cs
Value: 3
cloned value: 3

Value: 6
cloned value: 6

```