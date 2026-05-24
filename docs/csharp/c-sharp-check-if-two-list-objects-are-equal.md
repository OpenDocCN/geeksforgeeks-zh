# C# |检查两个列表对象是否相等

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-two-list-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-list-objects-are-equal/)

从 Object 类继承的 **Equals(Object)方法**用于检查指定的[列表<T>T3】对象是否等于另一个列表< T >对象。](https://www.geeksforgeeks.org/c-list-class/)

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to if a List object
// is equal to another List object
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an List<T> of Integers
        List<int> firstlist = new List<int>();

        // Adding elements to List
        firstlist.Add(17);
        firstlist.Add(19);
        firstlist.Add(21);
        firstlist.Add(9);
        firstlist.Add(75);
        firstlist.Add(19);
        firstlist.Add(73);

        // Checking whether firstlist is
        // equal to itself or not
        Console.WriteLine(firstlist.Equals(firstlist));
    }
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# program to if a List object
// is equal to another List object
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a List of strings
        List<string> list1 = new List<string>();

        // Inserting elements in List
        list1.Add("DS");
        list1.Add("C++");
        list1.Add("Java");
        list1.Add("JavaScript");

        // Creating an List<T> of Integers
        List<int> list2 = new List<int>();

        // Adding elements to List
        list2.Add(78);
        list2.Add(44);
        list2.Add(27);
        list2.Add(98);
        list2.Add(74);

        // Checking whether list1 is
        // equal to list2 or not
        Console.WriteLine(list1.Equals(list2));

        // Creating a List of integers
        List<int> list3 = new List<int>();

        // Assigning list2 to list3
        list3 = list2;

        // Checking whether list3 is
        // equal to list2 or not
        Console.WriteLine(list3.Equals(list2));
    }
}
```

**输出:**

```cs
False
True

```

**注意:**如果当前实例是引用类型， *Equals(对象)*方法检查引用是否相等。