# C# |检查指定的字符串是否在字符串集合

中

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-the-specific-string-collection/](https://www.geeksforgeeks.org/c-sharp-check-if-the-specified-string-is-in-the-stringcollection/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。

**StringCollection。Contains(String)** 方法用于检查指定的字符串是否在 StringCollection 中。

**语法:**

```cs
public bool Contains (string value);

```

这里，*值*是要在 StringCollection 中定位的字符串。该值可以为空。

**返回值:**如果在 StringCollection 中找到*值*，则该方法返回 ***true*** ，否则返回 ***false*** 。

**注:**

*   **包含**方法可以在执行进一步操作之前确认字符串的存在。
*   这个方法执行线性搜索，因此，这个方法是一个 O(n)运算，其中 n 是 Count。

下面的程序说明了*字符串集合的使用。包含(字符串)方法*:

**例 1 :**

```cs
// C# code to check if the specified
// string is in the StringCollection
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

        // checking if StringCollection
        // Contains "A"
        Console.WriteLine(myCol.Contains("A"));
    }
}
```

**Output:**

```cs
True

```

**例 2:**

```cs
// C# code to check if the specified
// string is in the StringCollection
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
        String[] myArr = new String[] { "2", "3", "4", "5", "6" };

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        // checking if StringCollection
        // Contains "8"
        Console.WriteLine(myCol.Contains("8"));
    }
}
```

**Output:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . contains？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.contains?view=netframework-4.7.2)