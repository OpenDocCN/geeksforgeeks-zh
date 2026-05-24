# C# |检查字符串集合是否为只读

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-the-string collection-只读/](https://www.geeksforgeeks.org/c-sharp-check-if-the-stringcollection-is-read-only/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。
T5】string collection。IsReadOnly 属性用于获取一个值，该值指示 StringCollection 是否为只读。

**语法:**

```cs
public bool IsReadOnly { get; }

```

**返回值:**该属性始终返回 false。

**注:**

*   只读集合在创建后不允许添加、移除或修改元素。
*   检索该属性的值是一个 O(1)操作。

**示例:**

```cs
// C# code to check if the
// StringCollection is read-only
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
        // read-only
        Console.WriteLine(myCol.IsReadOnly);
    }
}
```

**输出:**

```cs
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . is readonly？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.isreadonly?view=netframework-4.7.2)