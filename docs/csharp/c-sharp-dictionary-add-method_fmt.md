# C# 字典 Add() 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-dictionary-add-method/](https://www.geeksforgeeks.org/c-sharp-dictionary-add-method/)

`Dictionary<TKey, TValue>.Add()` 方法用于向字典中添加指定的键和值。

## 语法

```csharp
public void Add (TKey key, TValue value);
```

## 参数

* `key`：是要添加的元素的键。
* `value`：是元素添加的值。对于引用类型，该值可以为 `null`。

## 异常

* `ArgumentNullException`：如果密钥为空。
* `ArgumentException`：如果字典中已经存在相同关键字的元素。

以下是说明使用 `Dictionary<TKey, TValue>.Add()` 方法的程序：

### 例 1

```csharp
// C# code to add the specified key
// and value into the Dictionary
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Create a new dictionary 
        // of strings, with string keys.
        Dictionary<string, string> myDict = 
           new Dictionary<string, string>();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get count of key/value
        // pairs in myDict
        Console.WriteLine("Total key/value pairs in"+
                    " myDict are : " + myDict.Count);

        // Displaying the key/value
        // pairs in myDict
        Console.WriteLine("The key/value pairs"+
                           " in myDict are : ");

        foreach(KeyValuePair<string, string> kvp in myDict)
        {
            Console.WriteLine("Key = {0}, Value = {1}",
                              kvp.Key, kvp.Value);
        }
    }
}
```

**Output:**

```csharp
Total key/value pairs in myDict are : 6
The key/value pairs in myDict are : 
Key = Australia, Value = Canberra
Key = Belgium, Value = Brussels
Key = Netherlands, Value = Amsterdam
Key = China, Value = Beijing
Key = Russia, Value = Moscow
Key = India, Value = New Delhi
```

### 例 2

```csharp
// C# code to add the specified 
// key and value into the Dictionary
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

        // The Add method throws an
        // exception if the new key is
        // already in the dictionary.
        try {
            myDict.Add("Russia", "Moscow");
        }
        catch (ArgumentException) {
            Console.WriteLine("An element with Key "+
                         "= \"Russia\" already exists.");
        }
    }
}
```

**Output:**

```csharp
An element with Key = "Russia" already exists.
```

## 注

* 键不能为空，但如果 `TValue` 是引用类型，则值可以为空。
* 如果计数小于容量，此方法将接近 `O(1)` 操作。
* 如果容量必须增加以容纳新元素，则此方法变成 `O(n)` 操作，其中 `n` 是 `Count`。

## 参考

* [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2.add?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2.add?view=netframework-4.7.2)