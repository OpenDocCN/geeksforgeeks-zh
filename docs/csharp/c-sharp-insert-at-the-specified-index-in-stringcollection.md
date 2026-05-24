# C# |在 StringCollection 中的指定索引处插入

> 原文:[https://www . geeksforgeeks . org/c-sharp-insert-at-specific-index-in-string collection/](https://www.geeksforgeeks.org/c-sharp-insert-at-the-specified-index-in-stringcollection/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。
T5】string collection。Insert(Int32，String) 方法用于将字符串插入指定索引处的 StringCollection。

**语法:**

```cs
public void Insert (int index, string value);

```

**参数:**

*   **索引:**插入值的从零开始的索引。
*   **值:**要插入的字符串。该值可以为空。

**异常:**如果指数小于零 ***或*** 指数大于计数，此方法将给出*argumentout of range Exception*。

**注:**

*   StringCollection 中允许重复字符串。
*   如果*索引*等于计数，则值被添加到字符串集合的末尾。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

下面的程序说明了**字符串集合的使用。插入(Int32，String)方法:**

**例 1:**

```cs
// C# code to insert a string into
// the StringCollection at the
// specified index
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // Inserting elements into the string 
        // at specified indexes
        myCol.Insert(0, "A");
        myCol.Insert(1, "B");
        myCol.Insert(2, "F");
        myCol.Insert(3, "L");
        myCol.Insert(4, "Y");
        myCol.Insert(5, "Z");

        // Displaying the elements in StringCollection
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
F
L
Y
Z

```

**例 2:**

```cs
// C# code to insert a string into
// the StringCollection at the
// specified index
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // Inserting elements into the string
        // at specified indexes
        myCol.Insert(0, "2");
        myCol.Insert(1, "4");

        // This should raise exception
        // "ArgumentOutOfRangeException" as
        // index is less than 0
        myCol.Insert(-3, "6");

        myCol.Insert(3, "8");
        myCol.Insert(4, "10");
        myCol.Insert(5, "12");

        // Displaying the elements in StringCollection
        foreach(Object obj in myCol)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**输出:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:插入索引超出范围。必须是非负的并且小于或等于大小。
> 参数名称:索引

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . insert？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.insert?view=netframework-4.7.2)