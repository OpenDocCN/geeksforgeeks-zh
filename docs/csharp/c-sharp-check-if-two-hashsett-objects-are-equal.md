# C# |检查两个 HashSet <t>对象是否相等</t>

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-two-hashsett-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-hashsett-objects-are-equal/)

从 Object 类继承的 **Equals(Object)方法**用于检查指定的 [HashSet < T >](https://www.geeksforgeeks.org/c-sharp-hashset-class/) 对象是否等于另一个 HashSet < T >对象。

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里，obj 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to if a HashSet object
// is equal to another HashSet object
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a HashSet of strings
        HashSet<string> mySet = new HashSet<string>();

        // Inserting elements in HashSet
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
// C# program to if a HashSet object
// is equal to another HashSet object
using System;
using System.Collections.Generic;

class Geeks {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating a HashSet of strings
        HashSet<string> mySet1 = new HashSet<string>();

        // Inserting elements in HashSet
        mySet1.Add("HTML");
        mySet1.Add("CSS");
        mySet1.Add("PHP");
        mySet1.Add("DBMS");

        // Creating a HashSet of integers
        HashSet<int> mySet2 = new HashSet<int>();

        // Inserting elements in HashSet
        for (int i = 0; i < 5; i++) {
            mySet2.Add(i * 2);
        }

        // Checking whether mySet1 is
        // equal to mySet2 or not
        Console.WriteLine(mySet1.Equals(mySet2));

        // Creating a HashSet of integers
        HashSet<int> mySet3 = new HashSet<int>();

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