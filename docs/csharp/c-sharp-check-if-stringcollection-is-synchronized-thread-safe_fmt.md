# C# 检查 StringCollection 是否同步（线程安全）

> 原文：[https://www.geeksforgeeks.org/c-sharp-check-if-stringcollection-is-synchronized-thread-safe/](https://www.geeksforgeeks.org/c-sharp-check-if-stringcollection-is-synchronized-thread-safe/)

`StringCollection` 类是 .NET Framework 类库中表示字符串集合的类。`StringCollection` 类在 `System.Collections.Specialized` 命名空间中定义。
`StringCollection.IsSynchronized` 属性用于获取一个值，该值指示对 `StringCollection` 的访问是否同步（线程安全）。

## 语法

```cs
public bool IsSynchronized { get; }
```

## 返回值

该属性始终返回 `false`。

## 注意

检索该属性的值是一个 O(1) 运算。

## 示例

```cs
// C# code to check if StringCollection
// is synchronized (thread safe)
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
        // synchronized (thread safe)
        Console.WriteLine(myCol.IsSynchronized);
    }
}
```

## 输出

```cs
False
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.issynchronized?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.issynchronized?view=netframework-4.7.2)