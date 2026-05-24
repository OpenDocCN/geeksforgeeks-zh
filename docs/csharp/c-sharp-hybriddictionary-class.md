# C# |混合字典类

> 原文:[https://www . geesforgeks . org/c-sharp-hybrid dictionary-class/](https://www.geeksforgeeks.org/c-sharp-hybriddictionary-class/)

**杂交词典**尝试优化哈希表。它实现了一个链表和哈希表数据结构。当集合较小时，它通过使用列表字典来实现**词典**，当集合较大时，它通过使用**哈希表**来实现。

**杂交词典类的属性:**

*   对于字典中的元素数量未知的情况，建议使用此类。
*   它利用了具有小集合的**列表字典**的改进性能，并提供了切换到比列表字典更好地处理大集合的**哈希表**的灵活性。
*   如果集合的初始大小大于列表字典的最佳大小，则集合存储在哈希表中，以避免将元素从列表字典复制到哈希表的开销。
*   键不能为空，但值可以为空。

#### 构造器

| 构造器 | 描述 |
| **[【杂交词典()](https://www.geeksforgeeks.org/c-creating-an-empty-case-sensitive-hybriddictionary-class/)** | 创建一个区分大小写的空混合字典。 |
| **[【杂交词典(布尔)](https://www.geeksforgeeks.org/c-creating-an-empty-hybriddictionary-with-specified-case-sensitivity/)** | 创建具有指定区分大小写的空混合字典。 |
| **[【杂合词典(Int32)](https://www.geeksforgeeks.org/c-creating-a-case-sensitive-hybriddictionary-with-specified-initial-size/)** | 创建具有指定初始大小写的区分大小写的混合字典。 |
| **[【杂合词典(Int32，布尔)](https://www.geeksforgeeks.org/c-creating-a-hybriddictionary-with-specified-initial-size-case-sensitivity/)** | 创建具有指定初始大小写的混合字典。 |

**示例:**

```cs
// C# code to create a HybridDictionary
// with the specified initial size
// and case sensitivity.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary with the
        // specified initial size and case sensitivity.
        HybridDictionary myDict = new HybridDictionary(10, false);

        // Adding key/value pairs in myDict
        myDict.Add("I", "first");

        // This will not raise exception as the
        // Collection is not case-insensitive
        myDict.Add("i", "first");
        myDict.Add("II", "second");
        myDict.Add("III", "third");
        myDict.Add("IV", "fourth");
        myDict.Add("V", "fifth");

        // Displaying the key/value pairs in myDict
        foreach(DictionaryEntry de in myDict)
            Console.WriteLine(de.Key + " " + de.Value);
    }
}
```

**Output:**

```cs
III third
V fifth
II second
i first
I first
IV fourth

```

#### 性能

| 财产 | 描述 |
| **[计数](https://www.geeksforgeeks.org/c-count-the-number-of-key-value-pairs-in-hybriddictionary/)** | 获取混合字典中包含的键/值对的数量。 |
| **[【is fixed DSI】](https://www.geeksforgeeks.org/c-check-if-hybriddictionary-has-fixed-size/)** | 获取一个值，该值指示混合字典是否具有固定大小。 |
| **[【isreadonly】](https://www.geeksforgeeks.org/c-check-if-hybriddictionary-is-read-only/)** | 获取一个值，该值指示混合字典是否为只读。 |
| **[同步](https://www.geeksforgeeks.org/c-check-if-hybriddictionary-is-synchronized-thread-safe/)** | 获取一个值，该值指示混合字典是否同步(线程安全)。 |
| **[【物品】](https://www.geeksforgeeks.org/c-gets-or-sets-the-value-in-hybriddictionary-with-specified-key/)** | 获取或设置与指定键关联的值。 |
| **[键](https://www.geeksforgeeks.org/c-get-an-icollection-containing-the-keys-in-hybriddictionary/)** | 获取包含混合字典中的键的集合。 |
| 同步根 | 获取一个对象，该对象可用于同步对混合字典的访问。 |
| **[价值观](https://www.geeksforgeeks.org/c-get-an-icollection-containing-the-values-in-hybriddictionary/)** | 获取包含混合字典中的值的集合。 |

**例 1:**

```cs
// C# code to get the number of key/value
// pairs contained in the HybridDictionary.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("Australia", "Canberra");
        myDict.Add("Belgium", "Brussels");
        myDict.Add("Netherlands", "Amsterdam");
        myDict.Add("China", "Beijing");
        myDict.Add("Russia", "Moscow");
        myDict.Add("India", "New Delhi");

        // To get count of key/value pairs in myDict
        Console.WriteLine("Total key/value pairs in myDict are : " 
                                                  + myDict.Count);
    }
}
```

**Output:**

```cs
Total key/value pairs in myDict are : 6

```

**例 2:**

```cs
// C# code to check whether the
// HybridDictionary is read-only.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

        // To check whether the HybridDictionary
        // is read-only.
        Console.WriteLine(myDict.IsReadOnly);
    }
}
```

**Output:**

```cs
False

```

#### 方法

| 方法 | 描述 |
| **[添加(对象，对象)](https://www.geeksforgeeks.org/c-adding-the-specified-key-and-value-into-hybriddictionary/)** | 将具有指定键和值的条目添加到混合字典中。 |
| **[晴()](https://www.geeksforgeeks.org/c-removing-all-entries-from-hybriddictionary/)** | 从混合词典中删除所有条目。 |
| **[包含(对象)](https://www.geeksforgeeks.org/c-check-the-hybriddictionary-for-a-specific-key/)** | 确定混合字典是否包含特定的键。 |
| **[CopyTo(Array，Int32)](https://www.geeksforgeeks.org/c-copying-the-hybriddictionary-entries-to-an-array-instance/)** | 将混合字典条目复制到指定索引处的一维数组实例。 |
| **等于(对象)** | 确定指定的对象是否等于当前对象。 |
| **[【get 分子()](https://www.geeksforgeeks.org/c-get-an-enumerator-that-iterates-through-the-hybriddictionary/)** | 返回一个遍历混合字典的 IDictionaryEnumerator。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| gettype() | 获取当前实例的类型。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **[移除(对象)](https://www.geeksforgeeks.org/c-removing-the-specified-key-entry-from-hybriddictionary/)** | 从混合字典中移除具有指定键的条目。 |
| **ToString()** | 返回表示当前对象的字符串。 |

**例 1:**

```cs
// C# code to copy the HybridDictionary
// entries to a one-dimensional Array
// instance at the specified index.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

        // Creating a one-dimensional Array named myArr
        DictionaryEntry[] myArr = new DictionaryEntry[myDict.Count];

        // copying the HybridDictionary entries
        // to a one-dimensional Array instance
        // at the specified index
        myDict.CopyTo(myArr, 0);

        for (int i = 0; i < myArr.Length; i++)
            Console.WriteLine(myArr[i].Key + " --> " + myArr[i].Value);
    }
}
```

**Output:**

```cs
A --> Apple
B --> Banana
C --> Cat
D --> Dog
E --> Elephant
F --> Fish

```

**例 2:**

```cs
// C# code to remove the entry
// with the specified key from
// the HybridDictionary.
using System;
using System.Collections;
using System.Collections.Specialized;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a HybridDictionary named myDict
        HybridDictionary myDict = new HybridDictionary();

        // Adding key/value pairs in myDict
        myDict.Add("A", "Apple");
        myDict.Add("B", "Banana");
        myDict.Add("C", "Cat");
        myDict.Add("D", "Dog");
        myDict.Add("E", "Elephant");
        myDict.Add("F", "Fish");

        // Displaying the number of key/value
        // pairs in HybridDictionary myDict
        Console.WriteLine("Number of key/value pairs in myDict are : " 
                                                       + myDict.Count);

        // Removing the entry with the
        // specified key from the HybridDictionary.
        myDict.Remove("C");

        // Displaying the number of key/value
        // pairs in HybridDictionary myDict
        Console.WriteLine("Number of key/value pairs in myDict are : " 
                                                       + myDict.Count);
    }
}
```

**Output:**

```cs
Number of key/value pairs in myDict are : 6
Number of key/value pairs in myDict are : 5

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . hybrid dictionary？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.hybriddictionary?view=netframework-4.7.2)