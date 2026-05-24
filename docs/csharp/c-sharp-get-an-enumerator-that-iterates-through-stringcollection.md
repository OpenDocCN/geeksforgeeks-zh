# C# |获取遍历 StringCollection 的枚举器

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-a-enumerator-iterating-through-string collection/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-stringcollection/)

***StringCollection。GetEnumerator 方法*** 用于获取一个 string 分子，该分子遍历 **[StringCollection](https://www.geeksforgeeks.org/c-stringcollection-class/)** 。

**语法:**

```cs
public System.Collections.Specialized.StringEnumerator GetEnumerator ();
```

**返回值:**这个方法为 StringCollection 返回一个 string 分子。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to get an StringEnumerator
// that iterates through the StringCollection
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

        // taking an emumerator & 
        // using GetEnumerator method
        StringEnumerator myenum = myCol.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the collection
        // and MoveNext returns false.
        while (myenum.MoveNext())
            Console.WriteLine(myenum.Current);
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
// C# code to get an StringEnumerator
// that iterates through the StringCollection
using System;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // Adding elements in StringCollection
        myCol.Add("45");
        myCol.Add("78");
        myCol.Add("98");
        myCol.Add("12");
        myCol.Add("67");

        // taking an emumerator 
        // & using GetEnumerator method
        StringEnumerator myenum = myCol.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the collection
        // and MoveNext returns false.
        while (myenum.MoveNext())
            Console.WriteLine(myenum.Current);
    }
}
```

**Output:**

```cs
45
78
98
12
67

```

**注:**

*   C# 语言的 *foreach* 语句隐藏了枚举器的复杂性。因此，建议使用 *foreach* ，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   *当前*返回同一对象，直到调用*移动下一个*或*重置*为止。*移动下一个*将当前设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.getenumerator?view=netframework-4.7.2)