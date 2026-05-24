# C# |克隆()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-clone-method/](https://www.geeksforgeeks.org/c-sharp-clone-method/)

在 C# 中，Clone()是一个字符串方法。它用于克隆 string 对象，该对象返回该数据的另一个副本。
换句话说，它返回一个字符串实例的引用。返回值只是同一数据的另一个视图。直接在当前字符串实例上调用克隆方法。此方法不接受任何参数。

**语法:**

```cs
public object Clone()

```

**返回值类型:**系统。对象，或者我们可以说字符串的这个实例。

下面的程序说明了克隆()方法的使用:

```cs
// C# program to illustrate 
// Clone() method
using System;
class Geeks {

    // Main Method
    public static void Main(string[] args)
    {
        string s1 = "GeeksForgeeks";

        // Cannot implicitly convert 
        // type object to the string.
        // So explicit conversion 
        // using Clone() method
        string s2 = (String)s1.Clone();

        // Displaying both the string
        Console.WriteLine("String : {0}", s1);
        Console.WriteLine("Clone String : {0}", s2);
    }
}
```

**Output:**

```cs
String : GeeksForgeeks
Clone String : GeeksForgeeks

```

**参考:**[https://msdn . Microsoft . com/en-us/library/system . string . clone](https://msdn.microsoft.com/en-us/library/system.string.clone(v=vs.110).aspx?cs-save-lang=1&cs-lang=csharp# code-snippet-1)