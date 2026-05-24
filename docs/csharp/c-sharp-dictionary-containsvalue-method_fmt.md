# C# 字典.ContainsValue()方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-dictionary-containsvalue-method/](https://www.geeksforgeeks.org/c-sharp-dictionary-containsvalue-method/)

该方法用于检查字典是否包含特定值。

## 语法

```cs
public bool ContainsValue (TValue value);
```

在这里，`value`是要在字典中定位的值。引用类型的值可以是`null`。

## 返回值

如果字典中包含指定值的元素，该方法返回`true`，否则返回`false`。

以下是说明`Dictionary<TKey, TValue>.ContainsValue()`方法使用的程序：

## 示例 1

```cs
// C# code to check if a value
// is present or not in a Dictionary.
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new dictionary of
        // strings, with string keys.
        Dictionary<string, string> myDict =
          new Dictionary<string, string>();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Checking the value "India" but
        // here "India" is the key
        if (myDict.ContainsValue("India"))
            Console.WriteLine("Value : India is present.");
        else
            Console.WriteLine("Value : India is not present.");
    }
}
```

**输出：**

```cs
Value : India is not present.
```

## 示例 2

```cs
// C# code to check if a value is
// present or not in a Dictionary.
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Create a new dictionary of
        // strings, with string keys.
        Dictionary<string, string> myDict =
           new Dictionary<string, string>();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Checking for value Moscow
        if (myDict.ContainsValue("Moscow"))
            Console.WriteLine("Value : Moscow is present");
        else
            Console.WriteLine("Value : Moscow is absent");
    }
}
```

**输出：**

```cs
Value : Moscow is present
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2.containsvalue?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2.containsvalue?view=netframework-4.7.2)