# c# 中的 SortedDictionary 类

> 原文:[https://www . geeksforgeeks . org/sorted dictionary-class-in-c-sharp/](https://www.geeksforgeeks.org/sorteddictionary-class-in-c-sharp/)

在 C# 中，SortedDictionary <tkey>类用于表示键/值对的集合。这一对是排序的形式，排序是在键上完成的。该类在*系统下定义。集合.通用*命名空间。在 SortedDictionary 类中，键是不可变的，总是唯一的，并且不能为空。如果值类型是引用类型，则允许在值中使用 null。SortedDictionary 类为未排序的数据提供了最快的插入和移除操作。SortedDictionary 类的键/值对是通过使用 KeyValuePair 结构检索的。</tkey>

#### 构造器

T32】T33

| 构造器 | 描述 |
| **SortedDictionary<TKey，TValue > ()** | 初始化一个空的 sorted dictionary 类的新实例，并对键类型使用默认的 IComparer 实现。 |
| **SortedDictionary<TKey，tvvalue>(IComparer)** | 初始化 sorted dictionary 类的新实例，该实例为空，并使用指定的 I comparer 实现来比较键。 |
| **SortedDictionary<TKey，t value>(IDictionary)** | 初始化 sorted dictionary 类的新实例，该类包含从指定的 IDictionary 复制的元素，并使用键类型的默认 IComparer 实现。 |
| **SortedDictionary<TKey，tvvalue>(IDictionary，IComparer)** | 初始化 sorted dictionary 类的新实例，该类包含从指定的 IDictionary 复制的元素，并使用指定的 IComparer 实现来比较键。 |

**例:**

```cs
// C# program to illustrate the concept
// of SortedDictionary<TKey, TValue>()
// in SortedDictionary
using System;
using System.Collections.Generic;

public class GFG {

    // Main method
    static public void Main()
    {

        // Create a new SortedDictionary
        // of strings, with int keys.
        SortedDictionary<string, string> myDr = 
          new SortedDictionary<string, string>();

        // Adding key/value pairs in myDr
        myDr.Add("One", "C");
        myDr.Add("Two", "C++");
        myDr.Add("Three", "C#");

        // Display the key/value pairs
        foreach(KeyValuePair<string, string> pair in myDr)
        {
            Console.WriteLine("Key: {0} and Value: {1}",
                                  pair.Key, pair.Value);
        }
    }
}
```

**输出:**

```cs
Key: One and Value: C
Key: Three and Value: C#
Key: Two and Value: C++

```

#### 性能

| 财产 | 描述 |
| **比较器** | 获取用于排序字典元素的比较器。 |
| **[计数](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-count-property/)** | 获取 SortedDictionary 中包含的键/值对的数量。 |
| **[项【TKeY】](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-item-property/)** | 获取或设置与指定键关联的值。 |
| **[键](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-keys-property/)** | 获取包含 SortedDictionary 中的键的集合。 |
| **[Values](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-values-property/)** | 获取包含 SortedDictionary 中的值的集合。 |

**例:**

```cs
// C# program to illustrate the concept
// of count property in SortedDictionary
using System;
using System.Collections.Generic;

public class GFG {

    // Main method
    static public void Main()
    {

        // Create a new SortedDictionary
        // of strings, with int keys.
        SortedDictionary<int, string> myDr = 
        new SortedDictionary<int, string>();

        // Adding key/value pairs in myDr
        myDr.Add(1, "Dog");
        myDr.Add(2, "Cat");
        myDr.Add(3, "Birds");
        myDr.Add(4, "Rabbits");
        myDr.Add(5, "Fish");
        myDr.Add(6, "Hamster");
        myDr.Add(7, "Turtle");

        // Display the total number of 
        // key/value pairs present in myDr
        Console.WriteLine("Total number of pairs "+
              "present in myDr : {0}", myDr.Count);
    }
}
```

**输出:**

```cs
Total number of pairs present in myDr : 7

```