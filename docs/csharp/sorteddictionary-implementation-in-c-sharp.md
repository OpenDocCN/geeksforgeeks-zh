# c# 中的 SortedDictionary 实现

> 原文:[https://www . geeksforgeeks . org/sorted dictionary-implementation-in-c-sharp/](https://www.geeksforgeeks.org/sorteddictionary-implementation-in-c-sharp/)

在 C# 中，SortedDictionary 是一个通用集合，用于以排序的形式存储键/值对，并且对键进行排序。排序字典在*系统下定义。集合.泛型*命名空间。它本质上是动态的，意味着排序后的字典的大小会根据需要而增长。

**要点:**

*   **sorted dictionary 类实现了**
    *   收藏<keyvaluepair tvalue="">>界面</keyvaluepair>
    *   互动<tkey tvalue="">界面</tkey>
    *   IEnumerable <keyvaluepair tvalue="">>界面</keyvaluepair>
    *   IEnumerable <t>界面</t>
    *   ireadoptolcollection<keyvaluepair tvalue="">界面</keyvaluepair>
    *   IReadOnlyDictionary <tkey tvalue="">界面</tkey>
    *   收藏接口
    *   接口
    *   IEnumerable 接口
*   在 SortedDictionary 中，键必须是唯一的。不允许重复的键。
*   在 SortedDictionary 中，键是不可变的，不能为空。
*   在 SortedDictionary 中，当值的类型为引用类型时，该值可以为空。
*   它为未排序的数据提供了最快的插入和移除操作。
*   在 SortedDictionary 中，只能存储相同类型的键/值对。
*   SortedDictionary 的容量是 SortedDictionary 可以容纳的键/值对的数量。
*   它按升序排序。

#### 如何创建 SortedDictionary？

一个 SortedDictionary 类有 **4** 个构造函数，用于创建一个 SortedDictionary，构造函数如下:

*   **SortedDictionary < TKey，TValue > ():** 此构造函数用于创建 SortedDictionary 类的一个实例，该实例为空，并对键类型使用默认的 IComparer 实现。
*   **SortedDictionary < TKey，TValue > (IComparer):** 此构造函数用于创建 SortedDictionary 类的实例，该实例为空，并使用指定的 IComparer 实现来比较键。
*   **SortedDictionary < TKey，TValue > (IDictionary):** 此构造函数用于创建 SortedDictionary 类的实例，该类包含从指定的 IDictionary 复制的元素，并对键类型使用默认的 IComparer 实现。
*   **SortedDictionary < TKey，TValue > (IDictionary，IComparer):** 此构造函数用于创建 SortedDictionary 类的实例，该类包含从指定的 IDictionary 复制的元素，并使用指定的 IComparer 实现来比较键。

让我们看看如何使用 *SortedDictionary < TKey，TValue > ()* 构造函数创建 SortedDictionary:

**第一步:**包含*系统。集合。泛型*命名空间在你的程序中借助*使用*关键字。

```cs
using System.Collection.Generics;
```

**步骤 2:** 使用 SortedDictionary <创建一个 sorted dictionary TKey，TValue >类，如下所示:

> sorted dictionary<type_of_key type_of_value="">sorted dictionary _ name = new sorted dictionary<type_of_key type_of_value="">()；</type_of_key></type_of_key>

**第三步:**如果你想在你的排序字典中添加元素，那么使用 **[Add()方法](https://www.geeksforgeeks.org/csharp-sorteddictionary-add-method/)** 在你的排序字典中添加一个键/值对。您还可以使用集合初始值设定项在 SortedDictionary 中添加键/值对。

**步骤 4:** 通过使用 *foreach* 循环，或通过使用索引值，或通过使用 for 循环来访问 SortedDictionary 的键/值对。

**示例:**

```cs
// C# program to illustrate how 
// to create sorted dictionary
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating sorted dictionary
        // Using SortedDictionary class
        SortedDictionary<int, string> My_sdict = 
            new SortedDictionary<int, string>();

        // Adding key/value pair in Sorted 
        // Dictionary Using Add() method
        My_sdict.Add(004, "Ask.com");
        My_sdict.Add(003, "Yahoo");
        My_sdict.Add(001, "Google");
        My_sdict.Add(005, "AOL.com");
        My_sdict.Add(002, "Bing");
        Console.WriteLine("Top Search Engines:");

        // Accessing the key/value pair of the 
        // SortedDictionary Using foreach loop
        foreach(KeyValuePair<int, string> pair in My_sdict)
        {
            Console.WriteLine("Rank: {0} and Name: {1}",
                                  pair.Key, pair.Value);
        }

        // Creating another sorted dictionary
        // using SortedDictionary<TKey, TValue> class
        // adding key/value pairs
        // Using collection initializer
        SortedDictionary<int, string> My_sdict1 = 
              new SortedDictionary<int, string>() {
                                     {1, "Python"},
                                      {5, "Swift"},
                                 {2, "JavaScript"},
                                        {4, "Go" },
                                      {3, "Rust"}};

        Console.WriteLine("Top Programming Language in 2019: ");

        // Accessing the key/value pair of the 
        // SortedDictionary Using foreach loop
        foreach(KeyValuePair<int, string> pair in My_sdict1)
        {
            Console.WriteLine("Rank:{0} and Name: {1}",
                                 pair.Key, pair.Value);
        }
    }
}
```

**Output:**

```cs
Top Search Engines:
Rank: 1 and Name: Google
Rank: 2 and Name: Bing
Rank: 3 and Name: Yahoo
Rank: 4 and Name: Ask.com
Rank: 5 and Name: AOL.com
Top Programming Language in 2019: 
Rank:1 and Name: Python
Rank:2 and Name: JavaScript
Rank:3 and Name: Rust
Rank:4 and Name: Go
Rank:5 and Name: Swift

```

#### 如何从 SortedDictionary 中移除元素？

在 SortedDictionary 中，允许从 SortedDictionary 中移除元素。SortedDictionary <tkey tvalue="">类提供了两种不同的方法来移除元素，这两种方法是:</tkey>

*   **[Clear()](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-clear-method/) :** 此方法用于移除 SortedDictionary 中的所有元素。
*   **[【移除(TKey)](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-remove-method/) :** 此方法用于从 SortedDictionary 中移除具有指定键的元素。

**示例:**

```cs
// C# program to illustrate how to
// Remove key/value pair from the 
// SortedDictionary
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating sorted dictionary
        // Using SortedDictionary class
        SortedDictionary<int, string> My_sdict = 
             new SortedDictionary<int, string>();

        // Adding key/value pair in 
        // SortedDictionary Using 
        // the Add() method
        My_sdict.Add(001, "Google");
        My_sdict.Add(002, "Bing");
        My_sdict.Add(003, "Yahoo");
        My_sdict.Add(004, "Ask.com");
        My_sdict.Add(005, "AOL.com");

        // Initial number of key/value pairs
        Console.WriteLine("Key/Value pair: {0}",
                                My_sdict.Count);

        // After using Remove(TKey) method
        My_sdict.Remove(002);
        Console.WriteLine("Key/Value pair: {0}",
                                My_sdict.Count);

        // After using Clear() method
        My_sdict.Clear();
        Console.WriteLine("Key/Value pair: {0}",
                                My_sdict.Count);
    }
}
```

**Output:**

```cs
Key/Value pair: 5
Key/Value pair: 4
Key/Value pair: 0

```

#### 如何检查 SortedDictionary 中键/值对的可用性？

在 SortedDictionary 中，您可以检查给定的键或值是否存在于指定的 SortedDictionary 中。SortedDictionary <tkey tvalue="">类提供了两种不同的检查方法，这两种方法是:</tkey>

*   **[contains key(TKey)](https://www.geeksforgeeks.org/c-sharp-check-if-sorteddictionary-contains-the-specified-key-or-not/):**此方法用于确定 SortedDictionary 是否包含具有指定键的元素。
*   **[contains value(tvvalue)](https://www.geeksforgeeks.org/c-sharp-sorteddictionary-containsvalue-method/):**此方法用于确定 SortedDictionary 是否包含具有指定值的元素。

**示例:**

```cs
// C# program to illustrate how to
// check the given key/value pair 
// is exists or not in SortedDictionary
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating sorted dictionary
        // Using SortedDictionary class
        SortedDictionary<int, string> My_sdict =
             new SortedDictionary<int, string>();

        // Adding key/value pair 
        // in SortedDictionary
        // Using Add() method
        My_sdict.Add(001, "Google");
        My_sdict.Add(002, "Bing");
        My_sdict.Add(003, "Yahoo");
        My_sdict.Add(004, "Ask.com");
        My_sdict.Add(005, "AOL.com");

        // Using ContainsKey(TKey) method
        if (My_sdict.ContainsKey(004) == true) 
        {
            Console.WriteLine("Key Found..");
        }
        else
        {
            Console.WriteLine("Key Not Found..");
        }

        // Using ContainsValue(TValue) method
        if (My_sdict.ContainsValue("Baidu") == true)
        {
            Console.WriteLine("Value Found..");
        }

        else 
        {
            Console.WriteLine("Value Not Found..");
        }
    }
}
```

**Output:**

```cs
Key Found..
Value Not Found..

```