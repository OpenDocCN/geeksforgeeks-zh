# C# |检查哈希表是否包含特定的键

> 原文:[https://www . geesforgeks . org/c-sharp-check-a-hashtable-contains-a-specific-key-or-not/](https://www.geeksforgeeks.org/c-sharp-check-whether-a-hashtable-contains-a-specific-key-or-not/)

***哈希表。包含(对象)方法*** 用于检查 **[哈希表](https://www.geeksforgeeks.org/c-hashtable-class/)** 是否包含特定的键。

**语法:**

```cs
public virtual bool Contains (object key);
```

这里，*键*是位于哈希表中的对象类型的键。

**返回值:**如果哈希表包含具有指定键的元素，该方法返回 *true* ，否则返回 *false* 。

**异常:**如果*键*为空，此方法将给出 ***参数为空异常*** 。

**注:**

*   *[哈希表。ContainsKey(Object)方法](https://www.geeksforgeeks.org/c-check-if-the-hashtable-contains-a-specific-key/)* 也用于检查哈希表是否包含特定的键。此方法的行为与 Contains()方法相同。
*   包含实现 *IDictionary 的方法。包含*。它的行为与 ContainsKey 完全一样，这个方法是一个 O(1)操作。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to check whether the Hashtable
// contains a specific key or not
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

        // Checking if Hashtable contains
        // the key "Brazil"
        Console.WriteLine(myTable.Contains("d"));
    }
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# code to check whether the Hashtable
// contains a specific key or not
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a Hashtable
        Hashtable myTable = new Hashtable();

        // Adding elements in Hashtable
        myTable.Add("1", "C");
        myTable.Add("2", "C++");
        myTable.Add("3", "Java");
        myTable.Add("4", "Python");

        // Checking if Hashtable contains
        // the key null. It will give exception
        // ArgumentNullException
        Console.WriteLine(myTable.Contains(null));
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:键不能为空。
> 参数名称:键

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . contains？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.contains?view=netframework-4.7.2)