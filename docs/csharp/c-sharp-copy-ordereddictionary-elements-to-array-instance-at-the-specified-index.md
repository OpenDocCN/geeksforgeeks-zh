# C# |将有序字典元素复制到指定索引处的数组实例中

> 原文:[https://www . geeksforgeeks . org/c-sharp-copy-ordereddictionary-elements-to-array-instance-at-the-specific-index/](https://www.geeksforgeeks.org/c-sharp-copy-ordereddictionary-elements-to-array-instance-at-the-specified-index/)

**OrderedDictionary。CopyTo(Array，Int32)方法**用于将 OrderedDictionary 元素复制到指定索引处的一维 Array 对象。

**语法:**

```cs
public void CopyTo (Array array, int index);
```

**参数:**

> **数组:**是一维数组，是从 OrderedDictionary 复制的 DictionaryEntry 对象的目的地。数组必须具有从零开始的索引。
> 
> **索引:**是*数组*中开始复制的从零开始的索引。

**注:** *序字典。CopyTo(Array，Int32)方法*不提供任何保证来维护 OrderedDictionary 集合中元素的顺序。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to copy OrderedDictionary to
// Array instance at the specified index
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
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

        DictionaryEntry[] myArr = new DictionaryEntry[myDict.Count];

        // Copying OrderedDictionary to Array
        // instance at the specified index
        myDict.CopyTo(myArr, 0);

        // Displaying elements in myArr
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine(myArr[i].Key + "-->" 
                                + myArr[i].Value);
        }
    }
}
```

**输出:**

```cs
key3-->value3
key4-->value4
key5-->value5
key2-->value2
key1-->value1

```

**例 2:**

```cs
// C# code to copy OrderedDictionary to
// Array instance at the specified index
// that give ArgumentOutOfRangeException
// due to the negative index
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a orderedDictionary named myDict
        OrderedDictionary myDict = new OrderedDictionary();

        // Adding key and value in myDict
        myDict.Add("C", "1");
        myDict.Add("C++", "2");
        myDict.Add("Java", "3");
        myDict.Add("C#", "4");

        DictionaryEntry[] myArr = new DictionaryEntry[myDict.Count];

        // Copying OrderedDictionary to Array
        // instance at the specified index
        // This will raise "ArgumentOutOfRangeException"
        // as index is less than 0
        myDict.CopyTo(myArr, -2);

        // Displaying elements in myArr
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine(myArr[i].Key + "-->" 
                                + myArr[i].Value);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:要求非负数。
> 参数名称:arrayIndex

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordereddictionary . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary.copyto?view=netframework-4.7.2)