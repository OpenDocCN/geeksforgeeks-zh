# C# |在 StringCollection 中的指定索引处插入

> 原文：[https://www.geeksforgeeks.org/c-sharp-insert-at-the-specified-index-in-stringcollection/](https://www.geeksforgeeks.org/c-sharp-insert-at-the-specified-index-in-stringcollection/)

`StringCollection` 类是 .NET Framework 类库中表示字符串集合的类。`StringCollection` 类在 `System.Collections.Specialized` 命名空间中定义。

`StringCollection.Insert(Int32, String)` 方法用于将字符串插入到 `StringCollection` 的指定索引处。

## 语法

```cs
public void Insert (int index, string value);
```

## 参数

*   `index`：插入值的从零开始的索引。
*   `value`：要插入的字符串。该值可以为 `null`。

## 异常

如果 `index` 小于零或 `index` 大于 `Count`，此方法将给出 `ArgumentOutOfRangeException`。

## 注

*   `StringCollection` 中允许重复字符串。
*   如果 `index` 等于 `Count`，则值被添加到字符串集合的末尾。
*   这个方法是一个 O(n) 运算，其中 n 是 `Count`。

下面的程序说明了 `StringCollection.Insert(Int32, String)` 方法的使用：

## 示例 1

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

**输出：**

```cs
A
B
F
L
Y
Z
```

## 示例 2

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

**输出：**

> 未处理异常：
> System.ArgumentOutOfRangeException：插入索引超出范围。必须是非负的并且小于或等于大小。
> 参数名称：索引

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.insert?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.insert?view=netframework-4.7.2)