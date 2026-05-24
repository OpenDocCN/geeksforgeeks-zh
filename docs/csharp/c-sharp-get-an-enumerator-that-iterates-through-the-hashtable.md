# C# |获取遍历哈希表的枚举器

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-一个遍历哈希表的枚举器/](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-hashtable/)

**哈希表。GetEnumerator 方法**用于返回一个迭代哈希表的 IDictionaryEnumerator。

**语法:**

```cs
public virtual System.Collections.IDictionaryEnumerator GetEnumerator ();
```

**返回值:**为哈希表返回一个 IDictionaryEnumerator。

下面的程序说明了**哈希表的使用。GetEnumerator 方法:**

**例 1:**

```cs
// C# code to get an IDictionaryEnumerator
// that iterates through the Hashtable
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable named myhash
        Hashtable myhash = new Hashtable();

        // Adding key/value pairs in myhash
        myhash.Add("A", "Apple");
        myhash.Add("B", "Banana");
        myhash.Add("C", "Cat");
        myhash.Add("D", "Dog");
        myhash.Add("E", "Elephant");
        myhash.Add("F", "Fish");

        // To get an IDictionaryEnumerator
        // for the Hashtable.
        IDictionaryEnumerator myEnumerator = myhash.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the collection
        // and MoveNext returns false.
        while (myEnumerator.MoveNext())
            Console.WriteLine(myEnumerator.Key + " --> "
                              + myEnumerator.Value);
    }
}
```

**输出:**

```cs
B --> Banana
C --> Cat
A --> Apple
F --> Fish
D --> Dog
E --> Elephant

```

**例 2:**

```cs
// C# code to get an IDictionaryEnumerator
// that iterates through the Hashtable
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable named myhash
        Hashtable myhash = new Hashtable();

        // Adding key/value pairs in myhash
        myhash.Add("I", "first");
        myhash.Add("II", "second");
        myhash.Add("III", "third");
        myhash.Add("IV", "fourth");
        myhash.Add("V", "fifth");

        // To get an IDictionaryEnumerator
        // for the Hashtable.
        IDictionaryEnumerator myEnumerator = myhash.GetEnumerator();

        // If MoveNext passes the end of the
        // collection, the enumerator is positioned
        // after the last element in the collection
        // and MoveNext returns false.
        while (myEnumerator.MoveNext())
            Console.WriteLine(myEnumerator.Key + " --> "
                              + myEnumerator.Value);
    }
}
```

**输出:**

```cs
III --> third
IV --> fourth
V --> fifth
II --> second
I --> first

```

**注:**

*   C# 语言的 **foreach** 语句隐藏了枚举器的复杂性。因此，建议使用 foreach，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   **当前**返回相同的对象，直到调用**移动下一个**或重置。**移动下一个**将当前设置为下一个元素。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.getenumerator?view=netframework-4.7.2)