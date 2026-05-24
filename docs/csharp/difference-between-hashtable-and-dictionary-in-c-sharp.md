# c# 中哈希表和字典的区别

> 原文:[https://www . geesforgeks . org/c-sharp 中 hashtable 和 dictionary 的区别/](https://www.geeksforgeeks.org/difference-between-hashtable-and-dictionary-in-c-sharp/)

在 C# 中，字典是一个通用集合，通常用于存储键/值对。字典在*系统下定义。集合。泛型*命名空间。它本质上是动态的，意味着字典的大小会根据需要而增长。

**例:**

```cs
// C# program to illustrate Dictionary
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating a dictionary
        // using Dictionary<TKey, TValue> class
        Dictionary<string, string> My_dict = 
                    new Dictionary<string, string>();

        // Adding key/value pairs in the Dictionary
        // Using Add() method
        My_dict.Add("a.01", "C");
        My_dict.Add("a.02", "C++");
        My_dict.Add("a.03", "C#");

        foreach(KeyValuePair<string, string> element in My_dict)
        {
            Console.WriteLine("Key:- {0} and Value:- {1}", 
                              element.Key, element.Value);
        }
    }
}
```

**输出:**

```cs
Key:- a.01 and Value:- C
Key:- a.02 and Value:- C++
Key:- a.03 and Value:- C#

```

哈希表是基于键的哈希代码排列的键/值对的集合。或者换句话说，哈希表用于创建使用哈希表进行存储的集合。是*系统中定义的非泛型集合类型。集合*命名空间。在哈希表中，键对象必须是不可变的，只要它们在哈希表中用作键。

**例:**

```cs
// C# program to illustrate a hashtable
using System;
using System.Collections;

class GFG {

    // Main method
    static public void Main()
    {

        // Create a hashtable
        // Using Hashtable class
        Hashtable my_hashtable = new Hashtable();

        // Adding key/value pair in the hashtable
        // Using Add() method
        my_hashtable.Add("A1", "Welcome");
        my_hashtable.Add("A2", "to");
        my_hashtable.Add("A3", "GeeksforGeeks");

        foreach(DictionaryEntry element in my_hashtable)
        {
            Console.WriteLine("Key:- {0} and Value:- {1} ",
                               element.Key, element.Value);
        }
    }
}
```

**输出:**

```cs
Key:- A3 and Value:- GeeksforGeeks 
Key:- A2 and Value:- to 
Key:- A1 and Value:- Welcome 

```

#### 哈希表 Vs 字典

| 散列表 | 词典 |
| 哈希表是非泛型集合。 | 字典是一个通用的集合。 |
| 哈希表在系统下定义。集合命名空间。 | 字典在系统下定义。集合。通用命名空间。 |
| 在哈希表中，可以存储相同类型或不同类型的键/值对。 | 在字典中，可以存储相同类型的键/值对。 |
| 在哈希表中，不需要指定键和值的类型。 | 在字典中，必须指定键和值的类型。 |
| 由于装箱/拆箱，数据检索比字典慢。 | 由于没有装箱/拆箱，数据检索比 Hashtable 更快。 |
| 在哈希表中，如果你试图访问一个给定哈希表中不存在的键，那么它会给出空值。 | 在字典中，如果你试图访问一个在给定字典中不存在的键，那么它会给出错误。 |
| 它是线程安全的。 | 它也是线程安全的但只对公共静态成员有效。 |
| 它不维护存储值的顺序。 | 它始终保持存储值的顺序。 |