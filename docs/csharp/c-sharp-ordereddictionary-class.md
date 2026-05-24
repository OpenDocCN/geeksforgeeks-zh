# C# | OrderedDictionary 类

> 原文:[https://www . geeksforgeeks . org/c-sharp-ordereddictionary-class/](https://www.geeksforgeeks.org/c-sharp-ordereddictionary-class/)

**orderedddictionary 类**表示可由键或索引访问的键/值对的集合。它存在于*T3 系统中。收藏.专门命名空间*。

**有序字典类的属性:**

*   每个元素都是存储在 **DictionaryEntry** 对象中的键/值对。
*   一个键不能为**空**，但一个值可以。
*   OrderedDictionary 的元素不是按键排序的。
*   元素可以通过键或索引来访问。

#### 构造器

| 构造器 | 描述 |
| **orderedddictionary()** | 初始化有序字典类的新实例。 |
| **ordered dictionary(IEquality comparer)** | 使用指定的比较器初始化 OrderedDictionary 类的新实例。 |
| **OrderedDictionary(Int32)** | 使用指定的初始容量初始化 OrderedDictionary 类的新实例。 |
| **OrderedDictionary(Int32，iequalitcomparer)** | 使用指定的初始容量和比较器初始化 OrderedDictionary 类的新实例。 |
| **OrderedDictionary(SerializationInfo，StreamingContext)** | 使用指定的序列化信息和流上下文对象初始化可序列化的 OrderedDictionary 类的新实例。 |

**示例:**

```cs
// C# code to create a OrderedDictionary
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
        myDict.Add("1", "ONE");
        myDict.Add("2", "TWO");
        myDict.Add("3", "THREE");

        // Displaying the number of key/value
        // pairs in myDict
        Console.WriteLine(myDict.Count);

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " --> " + de.Value);
    }
}
```

**输出:**

```cs
3
1 --> ONE
2 --> TWO
3 --> THREE

```

#### 性能

| 财产 | 描述 |
| **[计数](https://www.geeksforgeeks.org/c-get-the-number-of-key-values-pairs-contained-in-ordereddictionary/)** | 获取有序字典集合中包含的键/值对的数量。 |
| **[【isreadonly】](https://www.geeksforgeeks.org/c-check-if-ordereddictionary-collection-is-read-only/)** | 获取一个值，该值指示 OrderedDictionary 集合是否是只读的。 |
| **[项【国际 32】](https://www.geeksforgeeks.org/c-ordereddictionary-itemobject-property/)** | 获取或设置指定索引处的值。 |
| **[【物品】](https://www.geeksforgeeks.org/c-ordereddictionary-itemobject-property/)** | 获取或设置具有指定键的值。 |
| **[键](https://www.geeksforgeeks.org/c-get-an-icollection-containing-keys-in-ordereddictionary/)** | 获取包含 OrderedDictionary 集合中的键的 ICollection 对象。 |
| **[价值观](https://www.geeksforgeeks.org/c-get-an-icollection-containing-values-in-ordereddictionary/)** | 获取一个 ICollection 对象，该对象包含 OrderedDictionary 集合中的值。 |

**例 1:**

```cs
// C# code to check if OrderedDictionary
// collection is read-only
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

        // Checking if OrderedDictionary
        // collection is read-only
        Console.WriteLine(myDict.IsReadOnly);
    }
}
```

**输出:**

```cs
False

```

**例 2:**

```cs
// C# code to get the number of
// key/values pairs contained
// in the OrderedDictionary
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
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");

        // To Get the number of key/values
        // pairs contained in the OrderedDictionary
        Console.WriteLine("Number of key/value pairs are : " 
                                            + myDict.Count);
    }
}
```

**输出:**

```cs
Number of key/value pairs are : 4

```

#### 方法

| 方法 | 描述 |
| **[添加(对象，对象)](https://www.geeksforgeeks.org/c-add-key-and-value-into-ordereddictionary-collection/)** | 将具有指定键和值的条目添加到具有最低可用索引的 OrderedDictionary 集合中。 |
| **[【ASR only()](https://www.geeksforgeeks.org/c-get-a-read-only-copy-of-the-ordereddictionary/)** | 返回当前 OrderedDictionary 集合的只读副本。 |
| **[晴()](https://www.geeksforgeeks.org/c-remove-all-elements-from-ordereddictionary/)** | 从 OrderedDictionary 集合中移除所有元素。 |
| **[包含(对象)](https://www.geeksforgeeks.org/c-check-if-ordereddictionary-collection-contains-a-specific-key/)** | 确定 OrderedDictionary 集合是否包含特定的键。 |
| **[CopyTo(Array，Int32)](https://www.geeksforgeeks.org/c-copy-ordereddictionary-elements-to-array-instance-at-the-specified-index/)** | 将 OrderedDictionary 元素复制到指定索引处的一维数组对象。 |
| **等于(对象)** | 确定指定的对象是否等于当前对象。 |
| **[【get 分子()](https://www.geeksforgeeks.org/c-get-an-idictionaryenumerator-object-in-ordereddictionary/)** | 返回一个 IDictionaryEnumerator 对象，该对象遍历有序字典集合。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| **GetObjectData(SerializationInfo，StreamingContext)** | 实现 ISerializable 接口并返回序列化 OrderedDictionary 集合所需的数据。 |
| **GetType()** | 获取当前实例的类型。 |
| **插入(Int32，Object，Object)** | 使用指定索引处的指定键和值，向 OrderedDictionary 集合中插入新条目。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **on 序列化(对象)** | 实现 ISerializable 接口，并在反序列化完成时由反序列化事件回调。 |
| **[移除(对象)](https://www.geeksforgeeks.org/c-remove-entry-with-specified-key-from-ordereddictionary/)** | 从 OrderedDictionary 集合中移除具有指定键的条目。 |
| **[移除 At(Int32)](https://www.geeksforgeeks.org/c-remove-the-entry-at-specified-index-from-ordereddictionary/)** | 从 OrderedDictionary 集合中移除指定索引处的条目。 |
| **ToString()** | 返回表示当前对象的字符串。 |

**例 1:**

```cs
// C# code to get a read-only
// copy of the OrderedDictionary
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

        // To Get a read-only copy of
        // the OrderedDictionary
        OrderedDictionary myDict_1 = myDict.AsReadOnly();

        // Checking if myDict_1 is read-only
        Console.WriteLine(myDict_1.IsReadOnly);
    }
}
```

**输出:**

```cs
True

```

**例 2:**

```cs
// C# code to remove the entry
// with the specified key from
// the OrderedDictionary
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

        // Displaying the number of element initially
        Console.WriteLine("Number of elements are : " + myDict.Count);

        // Displaying the elements in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " -- " + de.Value);

        // Removing the entry with the specified
        // key from the OrderedDictionary
        myDict.Remove("key2");

        // Displaying the number of element initially
        Console.WriteLine("Number of elements are : " + myDict.Count);

        // Displaying the elements in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " -- " + de.Value);
    }
}
```

**输出:**

```cs
Number of elements are : 5
key1 -- value1
key2 -- value2
key3 -- value3
key4 -- value4
key5 -- value5
Number of elements are : 4
key1 -- value1
key3 -- value3
key4 -- value4
key5 -- value5

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . ordered dictionary？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.ordereddictionary?view=netframework-4.7.2)