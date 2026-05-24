# C# |列表字典类

> 原文:[https://www.geeksforgeeks.org/c-sharp-listdictionary-class/](https://www.geeksforgeeks.org/c-sharp-listdictionary-class/)

**列表词典**是一个专门的集合。它属于*T3 系统。收藏.专门命名空间*。此类型表示非泛型字典类型。用 **[链表](https://www.geeksforgeeks.org/data-structures/linked-list/)** 实现。这个类是字典集合(系统)的简单实现。集合)。它实现了 **IDictionary** 方法和属性，建议使用少量元素(少于 10 个)。

**列表词典类特征:**

*   ListDictionary 是使用单链表的 [IDictionary](https://docs.microsoft.com/en-us/dotnet/api/system.collections.idictionary?view=netframework-4.7.2) 的简单实现。
*   如果元素数量为 10 或更少，它比哈希表更小更快。
*   如果性能对于大量元素很重要，就不应该使用 listdecurity。
*   列表词典中的项目没有任何保证的顺序。
*   一个键不能为**空**，但是一个值可以。

#### 构造器

| 构造器 | 描述 |
| **列表词典()** | 使用默认比较器创建一个空的列表字典。 |
| **列表词典(IComparer)** | 使用指定的比较器创建一个空的列表字典。 |

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

#### 性能

| 财产 | 描述 |
| **[计数](https://www.geeksforgeeks.org/c-get-the-number-of-key-value-pairs-contained-in-listdictionary/)** | 获取列表字典中包含的键/值对的数量。 |
| **[【is fixed DSI】](https://www.geeksforgeeks.org/c-check-if-listdictionary-has-a-fixed-size/)** | 获取一个值，该值指示列表词典是否具有固定大小。 |
| **[【isreadonly】](https://www.geeksforgeeks.org/c-check-if-listdictionary-is-read-only/)** | 获取一个值，该值指示列表词典是否为只读。 |
| **[同步](https://www.geeksforgeeks.org/c-check-if-listdictionary-is-synchronized-thread-safe/)** | 获取一个值，该值指示列表字典是否同步(线程安全)。 |
| **[【物品】](https://www.geeksforgeeks.org/c-get-or-set-the-value-associated-with-specified-key-in-listdictionary/)** | 获取或设置与指定键关联的值。 |
| **[键](https://www.geeksforgeeks.org/c-get-an-icollection-containing-the-keys-in-listdictionary/)** | 获取包含列表字典中的键的集合。 |
| 同步根 | 获取一个对象，该对象可用于同步对列表字典的访问。 |
| **[价值观](https://www.geeksforgeeks.org/c-get-an-icollection-containing-the-values-in-listdictionary/)** | 获取包含列表字典中的值的集合。 |

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

#### 方法

| 方法 | 描述 |
| **[添加(对象，对象)](https://www.geeksforgeeks.org/c-add-the-specified-key-and-value-into-the-listdictionary/)** | 将具有指定键和值的条目添加到列表字典中。 |
| **[晴()](https://www.geeksforgeeks.org/c-remove-all-entries-from-the-listdictionary/)** | 从列表词典中删除所有条目。 |
| **[包含(对象)](https://www.geeksforgeeks.org/c-check-if-listdictionary-contains-a-specific-key/)** | 确定列表字典是否包含特定的键。 |
| **[CopyTo(Array，Int32)](https://www.geeksforgeeks.org/c-copy-listdictionary-to-array-instance-at-the-specified-index/)** | 将列表字典条目复制到指定索引处的一维数组实例。 |
| **等于(对象)** | 确定指定的对象是否等于当前对象。 |
| **get numeric stepper()** | 返回一个遍历列表字典的 IDictionaryEnumerator。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| gettype() | 获取当前实例的类型。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **[移除(对象)](https://www.geeksforgeeks.org/c-remove-the-entry-with-specified-key-from-listdictionary/)** | 从列表字典中移除具有指定键的条目。 |
| **ToString()** | 返回表示当前对象的字符串。 |

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
    Console.WriteLine("Total number of elements in myDict are : " 
                                                  + myDict.Count);

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
    Console.WriteLine("Total key/value pairs in myDict are : " 
                                              + myDict.Count);

    // Displaying the key/value pairs in myDict

    Console.WriteLine("The key/value pairs in myDict are : ");

    foreach(DictionaryEntry de in myDict)
    {
        Console.WriteLine(de.Key + " " + de.Value);
    }

    // Removing all entries from the ListDictionary
    myDict.Clear();

    // To get count of key/value pairs in myDict
    Console.WriteLine("Total key/value pairs in myDict are : " 
                                              + myDict.Count);

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . specialized . list dictionary？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.listdictionary?view=netframework-4.7.2)