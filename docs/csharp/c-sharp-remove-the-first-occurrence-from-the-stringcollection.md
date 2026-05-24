# C# |从字符串集合中删除第一个匹配项

> 原文:[https://www . geesforgeks . org/c-sharp-从字符串集合中移除第一个出现的字符/](https://www.geeksforgeeks.org/c-sharp-remove-the-first-occurrence-from-the-stringcollection/)

StringCollection 类是。表示字符串集合的. NET Framework 类库。在 ***系统中定义了 StringCollection 类。收藏.专门**命名空间*。
T5】string collection。Remove(String) 方法用于从 StringCollection 中删除特定字符串的第一个匹配项。

**语法:**

```cs
public void Remove (string value);

```

这里，*值*是要从字符串集合中删除的字符串。该值可以为空。

**注:**

*   StringCollection 中允许重复字符串。
*   仅删除第一个匹配项。要删除所有出现的指定字符串，请在 IndexOf 不返回-1 时重复使用 *RemoveAt(IndexOf(值))*。
*   如果 StringCollection 不包含指定的对象，则 StringCollection 保持不变。不会引发异常。
*   此方法执行线性搜索；因此，这个方法是一个 O(n)运算，其中 n 是 Count。

**示例:**

```cs
// C# code to remove the first
// occurrence of a specific string
// from the StringCollection
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
        String[] myArr = new String[] {"A", "A", "A", "B", "C",
                                           "C", "D", "D", "E"};

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        Console.WriteLine("Elements in StringCollection are : ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);

        // Removing the first occurrence of
        // "A" from the StringCollection
        myCol.Remove("A");

        Console.WriteLine("Elements in StringCollection are : ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);

        // Removing the first occurrence of
        // "C" from the StringCollection
        myCol.Remove("C");

        Console.WriteLine("Elements in StringCollection are : ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);

        // Removing the first occurrence of
        // "A" from the StringCollection
        myCol.Remove("A");

        Console.WriteLine("Elements in StringCollection are : ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);

        // Removing the first occurrence of
        // "Z" from the StringCollection
        // It would not throw exception even
        // if "Z" does not exist in myCol
        myCol.Remove("Z");

        Console.WriteLine("Elements in StringCollection are : ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);
    }
}
```

**Output:**

```cs
Elements in StringCollection are : 
A
A
A
B
C
C
D
D
E
Elements in StringCollection are : 
A
A
B
C
C
D
D
E
Elements in StringCollection are : 
A
A
B
C
D
D
E
Elements in StringCollection are : 
A
B
C
D
D
E
Elements in StringCollection are : 
A
B
C
D
D
E

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . string collection . remove？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.remove?view=netframework-4.7.2)