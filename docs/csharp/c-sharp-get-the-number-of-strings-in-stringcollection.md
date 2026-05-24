# C# |获取 StringCollection 中的字符串个数

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-the-number-in-string collection/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-strings-in-stringcollection/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。

**StringCollection。Count** 属性用于获取 StringCollection 中包含的字符串数。

**语法:**

```cs
public int Count { get; }

```

**返回值:**返回 StringCollection 中包含的字符串数。

**注意:**检索该属性的值是一个 O(1)运算。

下面的程序说明了**字符串集合的使用。计数属性:**

**例 1:**

```cs
// C# code to get the number of strings
// contained in the StringCollection
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
        String[] myArr = new String[] { "First", "Second", "Third",
                                        "Fourth", "Fifth" };

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        // To get number of Strings contained
        // in the StringCollection
        Console.WriteLine("Number of strings in myCol are : " + myCol.Count);
    }
}
```

**Output:**

```cs
Number of strings in myCol are : 5

```

**例 2:**

```cs
// C# code to get the number of strings 
// contained in the StringCollection
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
        String[] myArr = new String[] {};

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        // To get number of Strings contained
        // in the StringCollection
        Console.WriteLine("Number of strings in myCol are : " 
                                              + myCol.Count);
    }
}
```

**Output:**

```cs
Number of strings in myCol are : 0

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.count?view=netframework-4.7.2)