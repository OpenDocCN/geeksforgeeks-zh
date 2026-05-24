# C# |检查两个数组列表对象是否相等

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-two-ArrayList-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-arraylist-objects-are-equal/)

**等于(对象)方法**继承自[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)，用于检查指定的数组列表对象是否等于另一个数组列表对象。

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to if a ArrayList
// is equal to itself or not
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a ArrayList
        ArrayList arrlist = new ArrayList();

        // Adding elements to ArrayList
        arrlist.Add(1);
        arrlist.Add(2);
        arrlist.Add(3);
        arrlist.Add(4);
        arrlist.Add(5);

        // Checking whether arrlistis
        // equal to itself or not
        Console.WriteLine(arrlist.Equals(arrlist));
    }
}
```

**输出:**

```cs
True

```

**示例 2:**equals 方法只检查两个数组列表引用是否引用同一个对象。如果两个对象不同，即使它们具有相同的值，它也会返回 false。

```cs
// C# program to if a ArrayList
// is equal to another ArrayList
using System;
using System.Collections;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a ArrayList
        ArrayList arrlist = new ArrayList();

        // Adding elements to ArrayList
        arrlist.Add("This");
        arrlist.Add("is");
        arrlist.Add("C#");
        arrlist.Add("ArrayList");
        arrlist.Add("Tutorial.");

        // Creating an ArrayList
        ArrayList arrlist2 = new ArrayList();

        // Adding elements to ArrayList
        arrlist2.Add("This");
        arrlist2.Add("is");
        arrlist2.Add("C#");
        arrlist2.Add("ArrayList");
        arrlist2.Add("Tutorial.");

        // Checking whether arrlist is
        // equal to arrlist2 or not
        Console.WriteLine(arrlist.Equals(arrlist2));

        // Creating a ArrayList
        ArrayList arrlist3 = new ArrayList();

        // Assigning arrlist2 to arrlist3
        arrlist3 = arrlist2;

        // Checking whether arrlist3 is
        // equal to arrlist2 or not
        Console.WriteLine(arrlist3.Equals(arrlist2));
    }
}
```

**输出:**

```cs
False
True

```

**注意:**如果当前实例是引用类型， *Equals(对象)*方法检查引用是否相等。