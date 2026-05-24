# C# | 字符串类

> 原文：`https://www.geeksforgeeks.org/c-sharp-stringdictionary-class/`

`StringDictionary` 是一个专门的集合。这个类属于 `System.Collections.Specialized` 命名空间。它只允许字符串键和字符串值。它存在性能问题。它实现了一个哈希表，其中键和值被强类型化为字符串而不是对象。

**特征:**

*   一个键不能为 `null`，但是一个值可以。
*   该键以不区分大小写的方式处理，即在与字符串字典一起使用之前将其转换为小写。
*   构造函数 `StringDictionary()` 初始化 `StringDictionary` 类的新实例。

## 构造器

| 构造器 | 描述 |
| --- | --- |
| `StringDictionary()` | 初始化 `StringDictionary` 类的新实例。 |

**示例:**

```cs
// C# code to create a StringDictionary
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
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");

// Displaying the keys and values in StringDictionary
        foreach(DictionaryEntry dic in myDict)
        {
            Console.WriteLine(dic.Key + " " + dic.Value);
        }
    }
}
```

**输出:**

```cs
d Dog
b Banana
c Cat
e Elephant
a Apple
```

## 性能

| 属性 | 描述 |
| --- | --- |
| `Count` | 获取字符串中键/值对的数量。 |
| `IsSynchronized` | 获取一个值，该值指示对 `StringDictionary` 的访问是否同步(线程安全)。 |
| `Item[String]` | 获取或设置与指定键关联的值。 |
| `Keys` | 获取 `StringDictionary` 中的键集合。 |
| `SyncRoot` | 获取一个对象，该对象可用于同步对 `StringDictionary` 的访问。 |
| `Values` | 获取 `StringDictionary` 中的值的集合。 |

**示例:**

```cs
// C# code illustrate the Properties of
// StringDictionary class
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
        myDict.Add("3", "prime & odd");
        myDict.Add("2", "prime & even");
        myDict.Add("4", "non-prime & even");
        myDict.Add("9", "non-prime & odd");

// -------- Values Property --------

// Getting a collection of values
        // in the StringDictionary
        foreach(string val in myDict.Values)
        {
            Console.WriteLine(val);
        }

// -------- IsSynchronized Property --------

// Checking if StringDictionary
        // is synchronized (thread safe)
        Console.WriteLine(myDict.IsSynchronized);
    }
}
```

**输出:**

```cs
prime & even
prime & odd
non-prime & odd
non-prime & even
False
```

## 方法

| 方法 | 描述 |
| --- | --- |
| `Add(String, String)` | 将具有指定键和值的条目添加到 `StringDictionary` 中。 |
| `Clear()` | 从字符串列表中删除所有条目。 |
| `ContainsKey(String)` | 确定 `StringDictionary` 是否包含特定的键。 |
| `ContainsValue(String)` | 确定 `StringDictionary` 是否包含特定值。 |
| `CopyTo(Array, Int32)` | 将字符串字典值复制到指定索引处的一维数组实例。 |
| `Equals(Object)` | 确定指定的对象是否等于当前对象。 |
| `GetEnumerator()` | 返回遍历字符串字典的枚举数。 |
| `GetHashCode()` | 用作默认哈希函数。 |
| `GetType()` | 获取当前实例的类型。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `Remove(String)` | 从字符串字典中移除具有指定键的条目。 |
| `ToString()` | 返回表示当前对象的字符串。 |

**例 1:**

```cs
// C# code to remove the entry
// with the specified key from
// the StringDictionary
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
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

// Displaying the keys and values in StringDictionary
        Console.WriteLine("The number of key/value pairs are : " + myDict.Count);

// Removing the entry with the specified
        // key from the StringDictionary
        myDict.Remove("D");

// Displaying the keys and values in StringDictionary
        Console.WriteLine("The number of key/value pairs are : " + myDict.Count);
    }
}
```

**输出:**

```cs
The number of key/value pairs are : 6
The number of key/value pairs are : 5
```

**例 2:**

```cs
// C# code to copy StringDictionary
// to Array at the specified index
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
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");

// Creating an Array named myArr
        DictionaryEntry[] myArr = { new DictionaryEntry(),
                                    new DictionaryEntry(),
                                    new DictionaryEntry(),
                                    new DictionaryEntry(),
                                    new DictionaryEntry() };

// Copying StringDictionary to
        // Array at the specified index
        myDict.CopyTo(myArr, 0);

// Displaying key and value pairs in Array myArr
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine(myArr[i].Key + " " + myArr[i].Value);
        }
    }
}
```

**输出:**

```cs
d Dog
b Banana
c Cat
e Elephant
a Apple
```

**参考:**

*   `https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.stringdictionary?view=netframework-4.7.2`