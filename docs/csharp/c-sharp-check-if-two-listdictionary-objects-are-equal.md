# C# |检查两个列表字典对象是否相等

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-two-list dictionary-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-listdictionary-objects-are-equal/)

**Equals(Object)方法**从[对象类](https://www.geeksforgeeks.org/c-object-class/)继承而来，用于检查指定的[列表字典](https://www.geeksforgeeks.org/c-listdictionary-class/)对象是否等于另一个列表字典对象。

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
// ListDictionary are equal or not
using System;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

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
// C# code to check if two
// ListDictionary are equal or not
using System;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a ListDictionary named myDict
        ListDictionary myDict1 = new ListDictionary();

        // Adding key/value pairs in myDict
        myDict1.Add("I", "first");
        myDict1.Add("II", "second");
        myDict1.Add("III", "third");
        myDict1.Add("IV", "fourth");
        myDict1.Add("V", "fifth");

        // Creating a ListDictionary named myDict2
        ListDictionary myDict2 = new ListDictionary();

        myDict2.Add("1st", "C");
        myDict2.Add("2nd", "C++");
        myDict2.Add("3rd", "Java");
        myDict2.Add("4th", "C#");
        myDict2.Add("5th", "HTML");
        myDict2.Add("6th", "PHP");

        // Checking whether myDict1 is
        // equal to myDict2 or not
        Console.WriteLine(myDict1.Equals(myDict2));

        // Creating a new ListDictionary
        ListDictionary myDict3 = new ListDictionary();

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