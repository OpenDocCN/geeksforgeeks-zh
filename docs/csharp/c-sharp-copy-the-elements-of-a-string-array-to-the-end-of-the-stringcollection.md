# C# |将字符串数组的元素复制到 StringCollection 的末尾

> 原文:[https://www . geeksforgeeks . org/c-sharp-将字符串数组的元素复制到字符串集合的末尾/](https://www.geeksforgeeks.org/c-sharp-copy-the-elements-of-a-string-array-to-the-end-of-the-stringcollection/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。

**StringCollection。AddRange(String[])** 方法用于将字符串数组的元素复制到 StringCollection 的末尾。

**语法:**

```cs
public void AddRange (string[] value);

```

这里，*字符串[]值*是一个字符串数组，它将被添加到 StringCollection 的末尾。数组本身不能为空，但它可以包含空元素。

**异常:**如果值为空，该方法将给出 *ArgumentNullException* 。

**注:**

*   StringCollection 接受 null 作为有效值，并允许重复元素。
*   如果 StringCollection 可以在不增加容量的情况下容纳新元素，那么这个方法就是 O(n)操作，其中 n 是要添加的元素数量。如果需要增加容量以容纳新元素，则此方法会变成 O(n + m)运算，其中 n 是要添加的元素数量，m 是 Count。

下面的程序说明了*字符串集合的使用。添加范围(字符串[])方法*:

**例 1:**

```cs
// C# code to copy the elements
// of a string array to the end
// of the StringCollection
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

        // Displaying elements in StringCollection
        foreach(Object obj in myCol)
        {
            Console.WriteLine("{0}", obj);
        }
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
// C# code to copy the elements
// of a string array to the end
// of the StringCollection
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

        // Displaying elements in StringCollection
        foreach(Object obj in myCol)
        {
            Console.WriteLine("{0}", obj);
        }
    }
}
```

**Output:**

```cs
2
3
4
5
6

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . addrange？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.addrange?view=netframework-4.7.2)