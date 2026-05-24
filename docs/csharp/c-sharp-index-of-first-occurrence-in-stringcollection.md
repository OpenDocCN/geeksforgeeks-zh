# C# |字符串集合中第一次出现的索引

> 原文:[https://www . geesforgeks . org/c-sharp-string collection 中第一次出现的索引/](https://www.geeksforgeeks.org/c-sharp-index-of-first-occurrence-in-stringcollection/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。
T5】string collection。方法用于搜索指定的字符串，该字符串返回 StringCollection 中第一个匹配项的从零开始的索引。

**语法:**

```cs
public int IndexOf (string value);

```

这里，*值*是要定位的字符串。该值可以为空。

**返回值:**该方法返回 StringCollection 中第一个出现的*值*的从零开始的索引，否则返回-1。

**注意:**该方法执行[线性搜索](https://www.geeksforgeeks.org/linear-search/)。因此，这个方法是一个 O(n)运算，其中 n 是 Count。

下面的程序说明了**字符串集合的使用。(字符串)**方法的索引:

**例 1:**

```cs
// C# code to search string and returns
// the zero-based index of the first
// occurrence in StringCollection
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
        String[] myArr = new String[] { "A", "B", "C", "C", "D" };

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        // To search string "C" and return
        // the zero-based index of the first
        // occurrence in StringCollection
        // Here, "C" exists at index 2 and 3.
        // But, the method should return 2
        Console.WriteLine(myCol.IndexOf("C"));
    }
}
```

**Output:**

```cs
2

```

**例 2:**

```cs
// C# code to search string and returns
// the zero-based index of the first
// occurrence in StringCollection
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

        // To search string "9" and return
        // the zero-based index of the first
        // occurrence in StringCollection
        // Here, "9" does not exist in myCol
        // Hence, method returns -1
        Console.WriteLine(myCol.IndexOf("9"));
    }
}
```

**Output:**

```cs
-1

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . indexof？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.indexof?view=netframework-4.7.2)