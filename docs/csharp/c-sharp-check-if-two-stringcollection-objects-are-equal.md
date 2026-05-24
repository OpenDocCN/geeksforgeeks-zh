# C# |检查两个 StringCollection 对象是否相等

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-two-string collection-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-stringcollection-objects-are-equal/)

**等于(对象)方法**继承自[对象类](https://www.geeksforgeeks.org/c-object-class/)，用于检查指定的[字符串集合](https://www.geeksforgeeks.org/c-stringcollection-class/)对象是否等于另一个字符串集合对象。

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to check if two
// StringCollections are equal or not
using System;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // Adding elements in StringCollection
        myCol.Add("A");
        myCol.Add("B");
        myCol.Add("C");
        myCol.Add("D");
        myCol.Add("E");

        // Checking whether myCol is
        // equal to itself or not
        Console.WriteLine(myCol.Equals(myCol));
    }
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# code to check if two
// StringCollections are equal or not
using System;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named my1
        StringCollection my1 = new StringCollection();

        // Adding elements in StringCollection
        my1.Add("GFG");
        my1.Add("Noida");
        my1.Add("DS");
        my1.Add("Geeks");
        my1.Add("Classes");

        // Creating a StringCollection named my2
        StringCollection my2 = new StringCollection();

        my2.Add("Australia");
        my2.Add("Belgium");
        my2.Add("Netherlands");
        my2.Add("China");
        my2.Add("Russia");
        my2.Add("India");

        // Checking whether my1 is
        // equal to my2 or not
        Console.WriteLine(my1.Equals(my2));

        // Creating a new StringCollection
        StringCollection my3 = new StringCollection();

        // Assigning my2 to my3
        my3 = my2;

        // Checking whether my3 is
        // equal to my2 or not
        Console.WriteLine(my3.Equals(my2));
    }
}
```

**输出:**

```cs
False
True

```

**注意:**如果当前实例是引用类型， *Equals(对象)*方法检查引用是否相等。