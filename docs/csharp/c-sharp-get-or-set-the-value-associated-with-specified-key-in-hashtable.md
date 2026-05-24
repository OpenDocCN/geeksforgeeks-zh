# C# |获取或设置哈希表

中与指定键关联的值

> 原文:[https://www . geesforgeks . org/c-sharp-get-or-set-value-associated-in-specified-key-in-hashtable/](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-value-associated-with-specified-key-in-hashtable/)

***哈希表。项目【对象】属性*** 用于获取或设置 **[哈希表](https://www.geeksforgeeks.org/c-hashtable-class/)** 中指定键的关联值。

**语法:**

```cs
public virtual object this[object key] { get; set; }
```

这里*键*是取值或设置值的对象类型的键。

**异常:**

*   **参数空异常:**如果*键*为空。
*   **notSupportDexception:**如果设置了属性并且哈希表是只读的。或者设置了属性，*键*在集合中不存在，哈希表有固定的大小。

**注:**

*   此属性返回与特定键关联的值。如果找不到该键，并且有人试图获取该键，则该属性将返回 null，如果试图设置，将导致创建具有指定键的新元素。
*   检索和设置该属性的值是一个 O(1)操作。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# code to Gets or sets the value
// associated with the specified key
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

        // Setting the value associated with key "c"
        myTable["c"] = "C#";

        Console.WriteLine("Updated Values:");

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
Updated Values:
d: data structures
c: C#
q: quiz
g: geeks

```

**例 2:**

```cs
// C# code to Gets or sets the value
// associated with the specified key
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

        // Setting the value associated
        // with key "56" which is not present 
        // will result in the creation of 
        // new key and value will be set which 
        // is given by the user
        myTable["56"] = "New Value";

        Console.WriteLine("Updated Values:");

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
Updated Values:
5: Odd and Prime
9: Odd
2: Even and Prime
56: New Value
4: Even

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . item？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.item?view=netframework-4.7.2)