# C# |检查两个排序集<t>对象是否相等</t>

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-if-two-sorted sett-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-sortedsett-objects-are-equal/)

从 Object 类继承的 **Equals(Object)方法**用于检查指定的 [SortedSet < T >](https://www.geeksforgeeks.org/c-sortedset-class/) 对象是否等于另一个 SortedSet < T >对象。

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to if a SortedSet object
// is equal to another SortedSet object
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySet = new SortedSet<string>();

        // Inserting elements in SortedSet
        mySet.Add("DS");
        mySet.Add("C++");
        mySet.Add("Java");
        mySet.Add("JavaScript");

        // Checking whether mySet is
        // equal to itself or not
        Console.WriteLine(mySet.Equals(mySet));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# program to if a SortedSet object
// is equal to another SortedSet object
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a SortedSet of strings
        SortedSet<string> mySet1 = new SortedSet<string>();

        // Inserting elements in SortedSet
        mySet1.Add("GeeksforGeeks");
        mySet1.Add("Noida");
        mySet1.Add("Data Structure");
        mySet1.Add("Noida");

        // Creating a SortedSet of integers
        SortedSet<int> mySet2 = new SortedSet<int>();

        // Inserting elements in SortedSet
        for (int i = 0; i < 5; i++) {
            mySet2.Add(i * 2);
        }

        // Checking whether mySet1 is
        // equal to mySet2 or not
        Console.WriteLine(mySet1.Equals(mySet2));

        // Creating a SortedSet of integers
        SortedSet<int> mySet3 = new SortedSet<int>();

        // Assigning mySet2 to mySet3
        mySet3 = mySet2;

        // Checking whether mySet3 is
        // equal to mySet2 or not
        Console.WriteLine(mySet3.Equals(mySet2));
    }
}
```

**Output:**

```cs
False
True

```

**注意:**如果当前实例是引用类型， *Equals(对象)*方法检查引用是否相等。