# C# 获取或设置 StringCollection 中指定索引处的元素

> 原文：[https://www.geeksforgeeks.org/c-sharp-gets-or-sets-the-element-at-the-specified-index-in-stringcollection/](https://www.geeksforgeeks.org/c-sharp-gets-or-sets-the-element-at-the-specified-index-in-stringcollection/)

`StringCollection.Item[Int32]` 属性用于获取或设置指定索引处的元素。

## 语法

```cs
public string this[int index] { get; set; }
```

这里，`index` 是要获取或设置的条目的从零开始的索引。

## 返回值

返回指定索引处的 `string` 类型的元素。

## 异常

如果 `index` 小于零或 `index` 等于或大于 `Count`，则该属性抛出 `ArgumentOutOfRangeException`。

以下程序说明了上述属性的使用：

## 例 1

```cs
// C# code to get or set the element at
// the specified index in StringCollection
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

Console.WriteLine("\nAfter Item[int32] Property: \n");

// setting the value at index 2
        myCol[2] = "Z";

// Displaying the elements
        // in the StringCollection
        foreach(Object obj1 in myCol)
        {
            Console.WriteLine(obj1);
        }
    }
}
```

## 输出

```cs
A
B
C
D
E

After Item[int32] Property:

A
B
Z
D
E
```

## 例 2

```cs
// C# code to get or set the element at
// the specified index in StringCollection
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
        myCol.Add("Geeks");
        myCol.Add("GFG");
        myCol.Add("DS");
        myCol.Add("Class");
        myCol.Add("Noida");

// Displaying objects in myCol
        foreach(Object obj in myCol)
        {
            Console.WriteLine(obj);
        }

Console.WriteLine("\nAfter Item[int32] Property: \n");

// setting the value at index 8
        // this will give error as index
        // is greater than count
        myCol[8] = "C#";

// Displaying the elements
        // in the StringCollection
        foreach(Object obj1 in myCol)
        {
            Console.WriteLine(obj1);
        }
    }
}
```

## 运行时错误

> 未处理异常:
> System.ArgumentOutOfRangeException: 索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称: 索引

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.item?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringcollection.item?view=netframework-4.7.2)