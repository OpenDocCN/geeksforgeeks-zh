# C# | 从字符串集合的指定索引中删除

> 原文: [https://www.geeksforgeeks.org/c-sharp-remove-from-the-specified-index-of-the-stringcollection/](https://www.geeksforgeeks.org/c-sharp-remove-from-the-specified-index-of-the-stringcollection/)

`StringCollection` 类是 .NET Framework 类库中表示字符串集合的类。`StringCollection` 类在 `System.Collections.Specialized` 命名空间中定义。
`StringCollection.RemoveAt(Int32)` 方法用于移除 `StringCollection` 中指定索引处的字符串。

## 语法

```cs
public void RemoveAt (int index);
```

这里，`index` 是要移除的字符串的从零开始的索引。

## 异常

如果 `index` 小于零或 `index` 等于或大于 `Count`，此方法将给出 `ArgumentOutOfRangeException`。

## 注

此方法为 O(n) 运算，其中 n 为 `Count`。

下面的程序说明了 `StringCollection.RemoveAt(Int32)` 方法的使用：

### 例 1

```cs
// C# code to remove the string at the
// specified index of the StringCollection
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

        Console.WriteLine("Elements in StringCollection myCol are : ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);

        // Removing element at index 3
        myCol.RemoveAt(3);

        Console.WriteLine("Elements in StringCollection myCol are : ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);
    }
}
```

**Output:**

```cs
Elements in StringCollection myCol are : 
A
B
C
D
E
Elements in StringCollection myCol are : 
A
B
C
E
```

### 例 2

```cs
// C# code to remove the string at the
// specified index of the StringCollection
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
        String[] myArr = new String[] { "1", "2", "3", "4", "5" };

        // Copying the elements of a string
        // array to the end of the StringCollection.
        myCol.AddRange(myArr);

        Console.WriteLine("Elements in StringCollection myCol are : ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);

        // Removing element at index -5
        // It should raise "ArgumentOutOfRangeException"
        // as index is less than 0
        myCol.RemoveAt(-5);

        Console.WriteLine("Elements in StringCollection myCol are : ");

        // Displaying elements in StringCollection
        // named myCol
        foreach(Object obj in myCol)
            Console.WriteLine(obj);
    }
}
```

**输出:**

> 未处理异常:
> System.ArgumentOutOfRangeException: 索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称: 索引

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.removeat?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.removeat?view=netframework-4.7.2)