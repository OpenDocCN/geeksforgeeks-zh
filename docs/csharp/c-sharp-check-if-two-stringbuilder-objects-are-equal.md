# C# |检查两个 StringBuilder 对象是否相等

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-if-two-string builder-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-stringbuilder-objects-are-equal/)

**StringBuilder。Equals 方法**用于检查该实例是否等于指定对象。

> **语法:**公共 bool Equals(系统。text . StringBuilder sb)；
> 在这里， *sb* 是一个可以和这个实例比较的对象，或者说是 null。
> 
> **返回值:**如果此实例和 *sb* 具有相等的字符串、容量和最大容量值，它将返回*true*；否则，为假。

**例 1:**

```cs
// C# program to if a StringBuilder object
// is equal to another StringBuilder object
using System;
using System.Text;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Create a StringBuilder object
        // with a String passed as parameter
        StringBuilder st1 = new StringBuilder("GeeksforGeeks");

        // Checking whether st1 is
        // equal to itself or not
        Console.WriteLine(st1.Equals(st1));
    }
}
```

**Output:**

```cs
True

```