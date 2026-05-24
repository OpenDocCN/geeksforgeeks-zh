# C# |检查两个有序字典对象是否相等

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-two-ordered dictionary-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-ordereddictionary-objects-are-equal/)

**等于(对象)方法**继承自[对象类](https://www.geeksforgeeks.org/c-object-class/)，用于检查指定的[有序字典](https://www.geeksforgeeks.org/c-ordereddictionary-class/)对象是否等于另一个有序字典对象。

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to check whether two
// OrderedDictionary objects
// are equal or not
using System;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a orderedDictionary named myDict
        OrderedDictionary myDict = new OrderedDictionary();

        // Adding key and value in myDict
        myDict.Add("1", "C");
        myDict.Add("2", "C++");
        myDict.Add("3", "Java");
        myDict.Add("4", "C#");

        // Checking whether myDict is
        // equal to itself or not
        Console.WriteLine(myDict.Equals(myDict));
    }
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# code to check whether two
// OrderedDictionary objects
// are equal or not
using System;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a OrderedDictionary named myDict
        OrderedDictionary myDict1 = new OrderedDictionary();

        // Adding key/value pairs in myDict
        myDict1.Add("I", "first");
        myDict1.Add("II", "second");
        myDict1.Add("III", "third");
        myDict1.Add("IV", "fourth");
        myDict1.Add("V", "fifth");

        // Creating a OrderedDictionary named myDict2
        OrderedDictionary myDict2 = new OrderedDictionary();

        myDict2.Add("Australia", "Canberra");
        myDict2.Add("Belgium", "Brussels");
        myDict2.Add("Netherlands", "Amsterdam");
        myDict2.Add("China", "Beijing");
        myDict2.Add("Russia", "Moscow");
        myDict2.Add("India", "New Delhi");

        // Checking whether myDict1 is
        // equal to myDict2 or not
        Console.WriteLine(myDict1.Equals(myDict2));

        // Creating a new OrderedDictionary
        OrderedDictionary myDict3 = new OrderedDictionary();

        // Assigning myDict2 to myDict3
        myDict3 = myDict2;

        // Checking whether myDict3 is
        // equal to myDict2 or not
        Console.WriteLine(myDict3.Equals(myDict2));
    }
}
```

**输出:**

```cs
False
True

```

**注意:**如果当前实例是引用类型， *Equals(对象)*方法检查引用是否相等。