# C# |在 StringCollection 的末尾添加一个字符串

> 原文:[https://www . geesforgeks . org/c-sharp-add-a-string-to-end-the-string collection/](https://www.geeksforgeeks.org/c-sharp-add-a-string-to-the-end-of-the-stringcollection/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。

**StringCollection。Add(String)** 方法用于在 StringCollection 的末尾添加一个字符串。

**语法:**

```cs
public int Add (string value);

```

这里，*值*是要添加到 StringCollection 末尾的字符串。该值可以为空。

**返回值:**新元素插入的从零开始的索引。

**注意:**如果计数小于容量，此方法为 O(1)运算。如果需要增加容量以容纳新元素，此方法将变成 O(n)操作，其中 n 是 Count。

下面的程序说明了**字符串集合的使用。添加(字符串)方法:**

**例 1:**

```cs
// C# code to add a string to the
// end of the StringCollection
using System;
using System.Collections;
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

        // Displaying objects in myCol
        foreach(Object obj in myCol)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**Output:**

```cs
A
B
C
D
E

```

**例 2:**

```cs
// C# code to add a string to the
// end of the StringCollection
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // Adding elements in StringCollection
        myCol.Add("2");
        myCol.Add("4");
        myCol.Add("6");
        myCol.Add("8");
        myCol.Add("10");

        // Displaying objects in myCol
        foreach(Object obj in myCol)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**Output:**

```cs
2
4
6
8
10

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . add？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.add?view=netframework-4.7.2)