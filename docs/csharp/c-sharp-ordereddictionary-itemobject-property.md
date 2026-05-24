# c# | orderedddictionary。项目[对象]属性

> 原文:[https://www . geesforgeks . org/c-sharp-ordereddictionary-item object-property/](https://www.geeksforgeeks.org/c-sharp-ordereddictionary-itemobject-property/)

此属性的重载列表中有两种方法，如下所示:

1.  **项[Int32] :** 用于获取或设置指定索引处的值。
2.  **项[对象] :** 用于获取或设置指定键的值。

#### OrderedDictionary。项目[Int32]属性

此属性用于获取或设置指定索引处的值。
**语法:**

```cs
public object this[int index] { get; set; }
```

这里， ***索引*** 是要获取或设置的值的从零开始的索引。
**返回值:**指定指标下的项目值。
**例外:**

*   **NotSupportedException :** 如果 OrderedDictionary 集合是只读的。
*   **argumentoutofrangerexception:**如果指数小于零 ***或*** 指数等于或大于 Count。

下面给出一些例子，以便更好地理解实现:
**例子 1:**

## c sharp . c sharp . c sharp . c sharp

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

**输出:**

```cs
value2
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

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

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:指数

**注意:**该属性允许您使用以下语法访问集合中的特定元素:**我的集合[索引]** 。

#### OrderedDictionary。项目[对象]属性

此属性用于获取或设置具有指定键的值。
**语法:**

```cs
public object this[object key] { get; set; }
```

这里， ***键*** 是获取或设置值的键。
**返回值:**与指定键关联的值。如果找不到指定的键，尝试获取它将返回 null，尝试设置它将使用指定的键创建一个新元素。
**异常:**如果正在设置属性并且 OrderedDictionary 集合是只读的，该属性将给出 **NotSupportedException** 。
**示例:**

## c sharp . c sharp . c sharp . c sharp

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

**输出:**

```cs
value3
```

**注:**

*   此属性允许您使用以下语法访问集合中的特定元素: **myCollection[key]** 。
*   键不能为空，但值可以为空。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary . item？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.item?view=netframework-4.7.2)