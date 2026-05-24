# C# | OrderedDictionary.Item[Object] 属性

> 原文：[https://www.geeksforgeeks.org/c-sharp-ordereddictionary-itemobject-property/](https://www.geeksforgeeks.org/c-sharp-ordereddictionary-itemobject-property/)

此属性的重载列表中有两种方法，如下所示：

1.  `Item[Int32]`：用于获取或设置指定索引处的值。
2.  `Item[Object]`：用于获取或设置指定键的值。

## OrderedDictionary.Item[Int32] 属性

此属性用于获取或设置指定索引处的值。

**语法：**

```cs
public object this[int index] { get; set; }
```

这里，`index` 是要获取或设置的值的从零开始的索引。

**返回值：** 指定索引下的项目值。

**例外：**

*   `NotSupportedException`：如果 `OrderedDictionary` 集合是只读的。
*   `ArgumentOutOfRangeException`：如果 `index` 小于零 **或** `index` 等于或大于 `Count`。

下面给出一些例子，以便更好地理解实现：

### 例子 1

```cs
// C# code to get or set the value
// at the specified index for
// OrderedDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a orderedDictionary named myDict
        OrderedDictionary myDict = new OrderedDictionary();

        // Adding key and value in myDict
        myDict.Add("key1", "value1");
        myDict.Add("key2", "value2");
        myDict.Add("key3", "value3");
        myDict.Add("key4", "value4");
        myDict.Add("key5", "value5");

        // To get or set the value at the
        // specified index for OrderedDictionary
        Console.WriteLine(myDict[1]);
    }
}
```

**输出：**

```cs
value2
```

### 例子 2

```cs
// C# code to get or set the value
// at the specified index for
// OrderedDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a orderedDictionary named myDict
        OrderedDictionary myDict = new OrderedDictionary();

        // Adding key and value in myDict
        myDict.Add("key1", "value1");
        myDict.Add("key2", "value2");
        myDict.Add("key3", "value3");
        myDict.Add("key4", "value4");
        myDict.Add("key5", "value5");

        // To get or set the value at the
        // specified index for OrderedDictionary
        // This should raise "ArgumentOutOfRangeException"
        // as index is less than 0
        Console.WriteLine(myDict[-3]);
    }
}
```

**运行时错误：**

> 未处理异常：
> System.ArgumentOutOfRangeException: 索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称: index

**注意：** 该属性允许您使用以下语法访问集合中的特定元素：`myCollection[index]`。

## OrderedDictionary.Item[Object] 属性

此属性用于获取或设置具有指定键的值。

**语法：**

```cs
public object this[object key] { get; set; }
```

这里，`key` 是获取或设置值的键。

**返回值：** 与指定键关联的值。如果找不到指定的键，尝试获取它将返回 `null`，尝试设置它将使用指定的键创建一个新元素。

**异常：** 如果正在设置属性并且 `OrderedDictionary` 集合是只读的，该属性将给出 `NotSupportedException`。

**示例：**

```cs
// C# code to get or set the
// value with the specified key
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver method
    public static void Main()
    {

        // Creating a orderedDictionary named myDict
        OrderedDictionary myDict = new OrderedDictionary();

        // Adding key and value in myDict
        myDict.Add("key1", "value1");
        myDict.Add("key2", "value2");
        myDict.Add("key3", "value3");
        myDict.Add("key4", "value4");
        myDict.Add("key5", "value5");

        // To get or set the value
        // with the specified key
        Console.WriteLine(myDict["key3"]);
    }
}
```

**输出：**

```cs
value3
```

**注：**

*   此属性允许您使用以下语法访问集合中的特定元素：`myCollection[key]`。
*   键不能为空，但值可以为空。

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.item?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.item?view=netframework-4.7.2)