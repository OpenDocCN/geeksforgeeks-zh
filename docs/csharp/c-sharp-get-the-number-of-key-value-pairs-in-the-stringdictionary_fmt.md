# C# | 获取字符串中键/值对的数量

> 原文：[https://www.geeksforgeeks.org/c-sharp-get-the-number-of-key-value-pairs-in-the-stringdictionary/](https://www.geeksforgeeks.org/c-sharp-get-the-number-of-key-value-pairs-in-the-stringdictionary/)

`StringDictionary.Count` 属性用于获取字符串中键/值对的数量。

## 语法

```cs
public virtual int Count { get; }
```

**返回值：** 返回字符串中键/值对的数量。

**注意：** 检索该属性的值是一个 O(1) 运算。

下面的程序说明了 `StringDictionary.Count` 属性的使用：

## 例 1

```cs
// C# code to get the number of key/value
// pairs in the StringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named myDict
        StringDictionary myDict = new StringDictionary();

        // Getting the number of key/value
        // pairs in the StringDictionary
        Console.Write("Number of key/value pairs in myDict are : ");
        Console.WriteLine(myDict.Count);
    }
}
```

**Output:**

```cs
Number of key/value pairs in myDict are : 0
```

## 例 2

```cs
// C# code to get the number of key/value
// pairs in the StringDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a StringDictionary named myDict
        StringDictionary myDict = new StringDictionary();

        // Adding key and value into the StringDictionary
        myDict.Add("G", "Geeks");
        myDict.Add("F", "For");
        myDict.Add("C", "C++");
        myDict.Add("DS", "Data Structures");
        myDict.Add("N", "Noida");

        // Getting the number of key/value
        // pairs in the StringDictionary
        Console.Write("Number of key/value pairs in myDict are : ");
        Console.WriteLine(myDict.Count);
    }
}
```

**Output:**

```cs
Number of key/value pairs in myDict are : 5
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.count?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary.count?view=netframework-4.7.2)