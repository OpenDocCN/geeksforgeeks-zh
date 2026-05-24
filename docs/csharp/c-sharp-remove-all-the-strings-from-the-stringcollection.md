# C# |从字符串集合中移除所有字符串

> 原文:[https://www . geesforgeks . org/c-sharp-从字符串集合中移除所有字符串/](https://www.geeksforgeeks.org/c-sharp-remove-all-the-strings-from-the-stringcollection/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。

**StringCollection。Clear** 方法用于从 StringCollection 中移除所有字符串。

**语法:**

```cs
public void Clear ();

```

**注:**

*   Count 被设置为零，并且集合元素对其他对象的引用也被释放。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**示例:**

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

        // creating a string array named myArr
        String[] myArr = new String[] {"Hello", "Geeks", 
                                "for", "GeeksforGeeks"};

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        Console.WriteLine("Initially elements in StringCollection are: ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);

        // Removing all the elements from StringCollection
        myCol.Clear();

        Console.WriteLine("After Removing: ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);
    }
}
```

**Output:**

```cs
Initially elements in StringCollection are: 
Hello
Geeks
for
GeeksforGeeks
After Removing:

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.clear?view=netframework-4.7.2)