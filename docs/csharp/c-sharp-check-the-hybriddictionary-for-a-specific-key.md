# C# |检查混合字典中的特定键

> 原文:[https://www . geesforgeks . org/c-sharp-check-the-hybrid dictionary-for-specific-key/](https://www.geeksforgeeks.org/c-sharp-check-the-hybriddictionary-for-a-specific-key/)

**杂交词典。Contains(Object)** 方法用于确定混合字典是否包含特定的键。

**语法:**

```cs
public bool Contains (object key);

```

这里，*键*是在杂交字典中定位的键。

**返回值:**如果混合字典包含指定关键字的条目，该方法将返回 ***真*** ，否则返回 ***假*** 。

**异常:**如果键为**空**，则该方法抛出 ***参数为空异常*** 。

以下是说明**杂交词典使用的程序。包含(对象)**方法:

**例 1:**

```cs
// C# code to check whether the
// HybridDictionary contains a specific key.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

        // To check whether the HybridDictionary
        // contains "G".
        Console.WriteLine(myDict.Contains("G"));

        // To check whether the HybridDictionary
        // contains "B".
        Console.WriteLine(myDict.Contains("B"));
    }
}
```

**输出:**

```cs
False
True

```

**例 2:**

```cs
// C# code to check whether the
// HybridDictionary contains a specific key.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("I", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // To check whether the HybridDictionary
        // contains "null". This should raise
        // "ArgumentNullException" as key is null
        Console.WriteLine(myDict.Contains(null));
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:键不能为空。
> 参数名称:键

**注:**此方法为 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary . contains？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary.contains?view=netframework-4.7.2)