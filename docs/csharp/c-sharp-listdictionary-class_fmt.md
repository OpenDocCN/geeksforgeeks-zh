# C# |列表字典类

> 原文:[https://www.geeksforgeeks.org/c-sharp-listdictionary-class/](https://www.geeksforgeeks.org/c-sharp-listdictionary-class/)

## 简介

**列表词典**是一个专门的集合。它属于`System.Collections.Specialized`命名空间。此类型表示非泛型字典类型。用**链表**实现。这个类是字典集合(`System.Collections`)的简单实现。它实现了`IDictionary`方法和属性，建议使用少量元素(少于 10 个)。

**列表词典类特征:**

*   `ListDictionary`是使用单链表的`IDictionary`的简单实现。
*   如果元素数量为 10 或更少，它比哈希表更小更快。
*   如果性能对于大量元素很重要，就不应该使用`ListDictionary`。
*   列表词典中的项目没有任何保证的顺序。
*   一个键不能为`null`，但是一个值可以。

## 构造器

| 构造器 | 描述 |
| --- | --- |
| `ListDictionary()` | 使用默认比较器创建一个空的列表字典。 |
| `ListDictionary(IComparer)` | 使用指定的比较器创建一个空的列表字典。 |

**示例:**

```cs
// C# code to create a ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " + myDict.Count);

        // Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6
The key/value pairs in myDict are : 
Australia Canberra
Belgium Brussels
Netherlands Amsterdam
China Beijing
Russia Moscow
India New Delhi
```

## 性能

| 属性 | 描述 |
| --- | --- |
| `Count` | 获取列表字典中包含的键/值对的数量。 |
| `IsFixedSize` | 获取一个值，该值指示列表词典是否具有固定大小。 |
| `IsReadOnly` | 获取一个值，该值指示列表词典是否为只读。 |
| `IsSynchronized` | 获取一个值，该值指示列表字典是否同步(线程安全)。 |
| `Item` | 获取或设置与指定键关联的值。 |
| `Keys` | 获取包含列表字典中的键的集合。 |
| `SyncRoot` | 获取一个对象，该对象可用于同步对列表字典的访问。 |
| `Values` | 获取包含列表字典中的值的集合。 |

**例 1:**

```cs
// C# code to get the number
// of key/value pairs contained
// in the ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Displaying the number of key/value
        // pairs contained in the ListDictionary
        Console.WriteLine(myDict.Count);
    }
}
```

**Output:**

```cs
6
```

**例 2:**

```cs
// C# code to check if ListDictionary is read-only
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Checking if ListDictionary is read-only
        Console.WriteLine(myDict.IsReadOnly);
    }
}
```

**Output:**

```cs
False
```

## 方法

| 方法 | 描述 |
| --- | --- |
| `Add(Object, Object)` | 将具有指定键和值的条目添加到列表字典中。 |
| `Clear()` | 从列表词典中删除所有条目。 |
| `Contains(Object)` | 确定列表字典是否包含特定的键。 |
| `CopyTo(Array, Int32)` | 将列表字典条目复制到指定索引处的一维数组实例。 |
| `Equals(Object)` | 确定指定的对象是否等于当前对象。 |
| `GetEnumerator()` | 返回一个遍历列表字典的`IDictionaryEnumerator`。 |
| `GetHashCode()` | 用作默认哈希函数。 |
| `GetType()` | 获取当前实例的类型。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `Remove(Object)` | 从列表字典中移除具有指定键的条目。 |
| `ToString()` | 返回表示当前对象的字符串。 |

**例 1:**

```cs
// C# code to add an entry with
// the specified key and value
// into the ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // Displaying the total number of elements in myDict
        Console.WriteLine("Total number of elements in myDict are : " + myDict.Count);

        // Displaying the elements in ListDictionary myDict
        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**Output:**

```cs
Total number of elements in myDict are : 6
Australia Canberra
Belgium Brussels
Netherlands Amsterdam
China Beijing
Russia Moscow
India New Delhi
```

**例 2:**

```cs
// C# code to remove all entries
// from the ListDictionary
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a ListDictionary named myDict
        ListDictionary myDict = new ListDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("I", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " + myDict.Count);

        // Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }

        // Removing all entries from the ListDictionary
        myDict.Clear();

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " + myDict.Count);

        // Displaying the key/value pairs in myDict
        Console.WriteLine("The key/value pairs in myDict are : ");

        foreach(DictionaryEntry de in myDict)
        {
            Console.WriteLine(de.Key + " " + de.Value);
        }
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 5
The key/value pairs in myDict are : 
I first
II second
III third
IV fourth
V fifth
Total key/value pairs in myDict are : 0
The key/value pairs in myDict are :
```

**参考:**

* [https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary?view=netframework-4.7.2)