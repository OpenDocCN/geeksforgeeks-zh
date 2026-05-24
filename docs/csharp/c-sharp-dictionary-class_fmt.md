# C# 字典类

> 原文：[https://www.geeksforgeeks.org/c-sharp-dictionary-class/](https://www.geeksforgeeks.org/c-sharp-dictionary-class/)

C# 中的 `Dictionary<TKey, TValue>` 类是键和值的集合。它是 `System.Collections.Generic` 命名空间中的一个通用集合类。`Dictionary<TKey, TValue>` 泛型类提供了一组键到一组值的映射。字典中的每一项都由一个值及其关联的键组成。通过使用其键检索值非常快，接近 `O(1)`，因为 `Dictionary` 类被实现为哈希表。根据字典的相等比较器，`Dictionary` 中的每个键都必须是唯一的。

注意：键不能为 `null`，但如果值类型 `TValue` 是引用类型，则值可以为 `null`。

## 参数

- `TKey`：表示字典中键的类型。
- `TValue`：表示字典中值的类型。

由于 `Dictionary<TKey, TValue>` 是键和值的集合，所以元素类型不是键的类型或值的类型。相反，元素类型是键类型和值类型的 `KeyValuePair<TKey, TValue>`。

## 构造函数

| 构造函数 | 描述 |
| --- | --- |
| `Dictionary<TKey, TValue>()` | 初始化 `Dictionary<TKey, TValue>` 类的新实例，该实例为空，具有默认的初始容量，并使用键类型的默认相等比较器。 |
| `Dictionary<TKey, TValue>(IDictionary<TKey, TValue>)` | 初始化 `Dictionary<TKey, TValue>` 类的新实例，该类包含从指定的 `IDictionary<TKey, TValue>` 复制的元素，并使用键类型的默认相等比较器。 |
| `Dictionary<TKey, TValue>(IDictionary<TKey, TValue>, IEqualityComparer<TKey>)` | 初始化 `Dictionary<TKey, TValue>` 类的新实例，该类包含从指定的字典复制的元素，并使用指定的 `IEqualityComparer<TKey>`。 |
| `Dictionary<TKey, TValue>(IEqualityComparer<TKey>)` | 初始化 `Dictionary<TKey, TValue>` 类的一个新实例，该实例为空，具有默认的初始容量，并使用指定的 `IEqualityComparer<TKey>`。 |
| `Dictionary<TKey, TValue>(Int32)` | 初始化 `Dictionary` 类的新实例，该实例为空，具有指定的初始容量，并使用键类型的默认相等比较器。 |
| `Dictionary<TKey, TValue>(Int32, IEqualityComparer<TKey>)` | 初始化 `Dictionary<TKey, TValue>` 类的一个新实例，该实例为空，具有指定的初始容量，并使用指定的 `IEqualityComparer<TKey>`。 |
| `Dictionary<TKey, TValue>(SerializationInfo, StreamingContext)` | 用序列化数据初始化 `Dictionary<TKey, TValue>` 类的新实例。 |

## 示例

### 示例 1

```cs
// C# code to create a Dictionary
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
        myDict.Add("1", "C");
        myDict.Add("2", "C++");
        myDict.Add("3", "Java");
        myDict.Add("4", "Python");
        myDict.Add("5", "C#");
        myDict.Add("6", "HTML");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs"+
              " in myDict are : " + myDict.Count);

        // Displaying the key/value pairs in myDict
        Console.WriteLine("\nThe key/value pairs"+
                           " in myDict are : ");

        foreach(KeyValuePair<string, string> kvp in myDict)
        {
            Console.WriteLine("Key = {0}, Value = {1}",
                              kvp.Key, kvp.Value);
        }
    }
}
```

**输出：**

```cs
Total key/value pairs in myDict are : 6

The key/value pairs in myDict are : 
Key = 1, Value = C
Key = 2, Value = C++
Key = 3, Value = Java
Key = 4, Value = Python
Key = 5, Value = C#
Key = 6, Value = HTML
```

## 属性

| 属性 | 描述 |
| --- | --- |
| `Comparer` | 获取用于确定字典键相等性的 `IEqualityComparer<TKey>`。 |
| [`Count`](https://www.geeksforgeeks.org/c-sharp-dictionary-count-property/) | 获取 `Dictionary<TKey, TValue>` 中包含的键/值对的数量。 |
| [`Item[TKey]`](https://www.geeksforgeeks.org/c-sharp-dictionary-item-property/) | 获取或设置与指定键关联的值。 |
| [`Keys`](https://www.geeksforgeeks.org/c-sharp-dictionary-keys-property/) | 获取包含 `Dictionary<TKey, TValue>` 中的键的集合。 |
| [`Values`](https://www.geeksforgeeks.org/c-sharp-dictionary-values-property/) | 获取包含 `Dictionary<TKey, TValue>` 中的值的集合。 |

### 示例 2

```cs
// C# code to get the keys
// in the Dictionary
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
        myDict.Add("1", "C");
        myDict.Add("2", "C++");
        myDict.Add("3", "Java");
        myDict.Add("4", "Python");
        myDict.Add("5", "C#");
        myDict.Add("6", "HTML");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs"+
              " in myDict are : " + myDict.Count);

        // To get the keys alone, use the Keys property.
        Dictionary<string, string>.KeyCollection keyColl =
                                              myDict.Keys;

        // The elements of the KeyCollection
        // are strongly typed with the type
        // that was specified for dictionary keys.
        foreach(string s in keyColl)
        {
            Console.WriteLine("Key = {0}", s);
        }
    }
}
```

**输出：**

```cs
Total key/value pairs in myDict are : 6
Key = 1
Key = 2
Key = 3
Key = 4
Key = 5
Key = 6
```

### 示例 3

```cs
// C# code to get the values
// in the Dictionary
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
        myDict.Add("1", "C");
        myDict.Add("2", "C++");
        myDict.Add("3", "Java");
        myDict.Add("4", "Python");
        myDict.Add("5", "C#");
        myDict.Add("6", "HTML");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs"+
              " in myDict are : " + myDict.Count);

        // To get the values alone, use the Values property.
        Dictionary<string, string>.ValueCollection valueColl =
                                                myDict.Values;

        // The elements of the ValueCollection
        // are strongly typed with the type
        // that was specified for dictionary values.
        foreach(string s in valueColl)
        {
            Console.WriteLine("Value = {0}", s);
        }
    }
}
```

**输出：**

```cs
Total key/value pairs in myDict are : 6
Value = C
Value = C++
Value = Java
Value = Python
Value = C#
Value = HTML
```

## 方法

| 方法 | 描述 |
| --- | --- |
| `Add(TKey, TValue)` | 将指定的键和值添加到字典中。 |
| [`Clear()`](https://www.geeksforgeeks.org/c-sharp-dictionary-clear-method/) | 从 `Dictionary<TKey, TValue>` 中删除所有键和值。 |
| [`ContainsKey(TKey)`](https://www.geeksforgeeks.org/c-sharp-dictionary-containskey-method/) | 确定 `Dictionary<TKey, TValue>` 是否包含指定的键。 |
| [`ContainsValue(TValue)`](https://www.geeksforgeeks.org/c-sharp-dictionary-containsvalue-method/) | 确定 `Dictionary<TKey, TValue>` 是否包含特定值。 |
| [`Equals(Object)`](https://www.geeksforgeeks.org/check-if-two-dictionary-objects-are-equal-in-c-sharp/) | 确定指定的对象是否等于当前对象。 |
| [`GetEnumerator()`](https://www.geeksforgeeks.org/c-sharp-get-an-enumerator-that-iterates-through-the-dictionary/) | 返回遍历 `Dictionary<TKey, TValue>` 的枚举数。 |
| `GetHashCode()` | 用作默认哈希函数。 |
| `GetObjectData(SerializationInfo, StreamingContext)` | 实现 `ISerializable` 接口并返回序列化 `Dictionary<TKey, TValue>` 实例所需的数据。 |
| `GetType()` | 获取当前实例的类型。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `OnDeserialization(Object)` | 实现 `ISerializable` 接口，并在反序列化完成时引发反序列化事件。 |
| [`Remove(TKey)`](https://www.geeksforgeeks.org/c-sharp-dictionary-remove-method/) | 从 `Dictionary<TKey, TValue>` 中删除带有指定键的值。 |
| `ToString()` | 返回表示当前对象的字符串。 |
| `TryGetValue(TKey, TValue)` | 获取与指定键关联的值。 |

## C#

```cs
// C# code to remove all entries
//  from Dictionary
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
        myDict.Add("1", "C");
        myDict.Add("2", "C++");
        myDict.Add("3", "Java");
        myDict.Add("4", "Python");
        myDict.Add("5", "C#");
        myDict.Add("6", "HTML");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs "+
                "in myDict are : " + myDict.Count);

        myDict.Clear();

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in "+
             "myDict after Clear() operation are : " +
                                        myDict.Count);
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6
Total key/value pairs in myDict after Clear() operation are : 0
```

## 例 2: C#

```cs
// C# code to remove the entry with
// the specified key from the Dictionary
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
        myDict.Add("1", "C");
        myDict.Add("2", "C++");
        myDict.Add("3", "Java");
        myDict.Add("4", "Python");
        myDict.Add("5", "C#");
        myDict.Add("6", "HTML");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs "+
                "in myDict are : " + myDict.Count);

        // Remove the entry with the
        // specified key from the Dictionary
        myDict.Remove("Russia");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in"+
          " myDict after Remove() operation are : " +
                                   myDict.Count);
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6
Total key/value pairs in myDict after Remove() operation are : 6
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.dictionary-2?view=netframework-4.7.2)