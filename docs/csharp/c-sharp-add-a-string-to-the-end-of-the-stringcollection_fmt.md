# C# | 在 StringCollection 的末尾添加一个字符串

> 原文：`https://www.geeksforgeeks.org/c-sharp-add-a-string-to-the-end-of-the-stringcollection/`

`StringCollection` 类是 .NET Framework 类库中表示字符串集合的类。`StringCollection` 类定义在 `System.Collections.Specialized` 命名空间中。

## 方法说明

`StringCollection.Add(String)` 方法用于在 `StringCollection` 的末尾添加一个字符串。

## 语法

```cs
public int Add (string value);
```

这里，`value` 是要添加到 `StringCollection` 末尾的字符串。该值可以为 `null`。

## 返回值

新元素插入的从零开始的索引。

## 注意事项

如果 `Count` 小于容量，此方法为 O(1) 运算。如果需要增加容量以容纳新元素，此方法将变成 O(n) 操作，其中 `n` 是 `Count`。

## 示例

下面的程序说明了 `StringCollection.Add(String)` 方法的使用。

### 例 1

```cs
// C# code to add a string to the
// end of the StringCollection
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // Adding elements in StringCollection
        myCol.Add("A");
        myCol.Add("B");
        myCol.Add("C");
        myCol.Add("D");
        myCol.Add("E");

        // Displaying objects in myCol
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
C
D
E
```

### 例 2

```cs
// C# code to add a string to the
// end of the StringCollection
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // creating a StringCollection named myCol
        StringCollection myCol = new StringCollection();

        // Adding elements in StringCollection
        myCol.Add("2");
        myCol.Add("4");
        myCol.Add("6");
        myCol.Add("8");
        myCol.Add("10");

        // Displaying objects in myCol
        foreach(Object obj in myCol)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**Output:**

```cs

```

## 参考

* `https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.add?view=netframework-4.7.2`