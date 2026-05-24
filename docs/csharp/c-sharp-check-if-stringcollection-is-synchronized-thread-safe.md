# C# |检查 StringCollection 是否同步(线程安全)

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-string collection-is-synchronized-thread-safe/](https://www.geeksforgeeks.org/c-sharp-check-if-stringcollection-is-synchronized-thread-safe/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。
T5】string collection。IsSynchronized 属性用于获取一个值，该值指示对 StringCollection 的访问是否同步(线程安全)。

**语法:**

```cs
public bool IsSynchronized { get; }

```

**返回值:**该属性始终返回 false。

**注意:**检索该属性的值是一个 O(1)运算。

**示例:**

```cs
// C# code to check if StringCollection
// is synchronized (thread safe)
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // creating a string array named myArr
        String[] myArr = new String[] { "A", "B", "C", "D", "E" };

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        // checking if StringCollection is
        // synchronized (thread safe)
        Console.WriteLine(myCol.IsSynchronized);
    }
}
```

**Output:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . is synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.issynchronized?view=netframework-4.7.2)