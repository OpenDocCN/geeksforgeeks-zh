# C# |向哈希表中添加元素

> 原文:[https://www . geeksforgeeks . org/c-sharp-在哈希表中添加元素/](https://www.geeksforgeeks.org/c-sharp-adding-an-element-into-the-hashtable/)

哈希表类表示基于键的哈希代码组织的**键和值对**的集合。该键用于访问集合中的项。**哈希表。Add(Object，Object)方法**用于将具有指定键和值的元素添加到哈希表中。

**语法:**

```cs
public virtual void Add(object key, object value);

```

**参数:**

> **键:**是要添加的*系统类型元素的指定键。对象*。
> 
> **值:**是要添加的类型为*系统的元素的指定值。对象*。*值*可以为*空*。

**异常:**

*   **参数空异常**:如果*键*为*空*。
*   **参数异常**:如果哈希表中已经存在具有相同*键*的元素。
*   **notSupportDexception**:哈希表要么是只读的，要么是哈希表的大小是固定的。

下面给出了一些例子，以便更好地理解实现:

**例 1 :**

```cs
// C# code for adding an element with the
// specified key and value into the Hashtable
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable
        Hashtable myTable = new Hashtable();

        // Adding elements in Hashtable
        myTable.Add("g", "geeks");
        myTable.Add("c", "c++");
        myTable.Add("d", "data structures");
        myTable.Add("q", "quiz");

        // Get a collection of the keys.
        ICollection c = myTable.Keys;

        // Displaying the contents
        foreach(string str in c)
            Console.WriteLine(str + ": " + myTable[str]);
    }
}
```

**Output:**

```cs
d: data structures
c: c++
q: quiz
g: geeks

```

**例 2:**

```cs
// C# code for adding an element with the
// specified key and value into the Hashtable
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable
        Hashtable myTable = new Hashtable();

        // Adding elements in Hashtable
        myTable.Add("4", "Even");
        myTable.Add("9", "Odd");
        myTable.Add("5", "Odd and Prime");
        myTable.Add("2", "Even and Prime");

        // Get a collection of the keys.
        ICollection c = myTable.Keys;

        // Displaying the contents
        foreach(string str in c)
            Console.WriteLine(str + ": " + myTable[str]);
    }
}
```

**Output:**

```cs
5: Odd and Prime
9: Odd
2: Even and Prime
4: Even

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.add?view=netframework-4.7.2)