# C# | CharEnumerator。GetHashCode()方法

> 原文:[https://www . geesforgeks . org/c-sharp-charenumerator-gethashcode-method/](https://www.geeksforgeeks.org/c-sharp-charenumerator-gethashcode-method/)

**GetHashCode()方法**作为默认的哈希函数，返回当前对象的哈希代码。该方法继承自[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)。

**语法:**

```cs
public virtual int GetHashCode ();
```

**返回值:**该方法返回一个与当前对象的哈希码对应的 Int32 值。

下面是说明使用**字符枚举器的程序。GetHashCode()** 方法:

**例 1:**

```cs
// C# program to illustrate the use
// of CharEnumerator.GetHashCode()
// Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "GeeksforGeeks is fun";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum1 = str.GetEnumerator();

        // Instantiate another CharEnumerator object
        CharEnumerator chEnum2 = str.GetEnumerator();

        // Printing the Hash Code of
        // both the CharEnumerator objects
        Console.WriteLine(chEnum1.GetHashCode());
        Console.WriteLine(chEnum2.GetHashCode());
    }
}
```

**Output:**

```cs
-381312627
1646495825

```

**例 2:**

```cs
// C# program to illustrate the use
// of CharEnumerator.GetHashCode()
// Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Initialize two string object
        string str1 = "GeeksforGeeks is fun",
                  str2 = "C C++ Java Python";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum1 = str1.GetEnumerator();

        // Instantiate another CharEnumerator object
        CharEnumerator chEnum2 = str2.GetEnumerator();

        // Printing the Hash Code of
        // both the CharEnumerator objects
        Console.WriteLine(chEnum1.GetHashCode());
        Console.WriteLine(chEnum2.GetHashCode());
    }
}
```

**Output:**

```cs
491910500
-1775248344

```