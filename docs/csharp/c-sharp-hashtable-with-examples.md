# 带示例的 C# 哈希表

> 原文:[https://www . geeksforgeeks . org/c-sharp-hashtable-with-examples/](https://www.geeksforgeeks.org/c-sharp-hashtable-with-examples/)

哈希表是基于键的哈希代码排列的键/值对的集合。或者换句话说，哈希表用于创建使用哈希表进行存储的集合。它通常通过计算每个键的哈希代码来优化查找，并自动存储到另一个篮子中，当您从哈希表中访问值时，它会将哈希代码与指定的键进行匹配。是*系统中定义的非泛型集合类型。集合*命名空间。

**要点:**

*   在哈希表中，键不能为空，但值可以为空。
*   在哈希表中，键对象必须是不可变的，只要它们在哈希表中用作键。
*   哈希表的容量是哈希表可以容纳的元素数量。
*   哈希表中的每个键对象都提供了一个哈希函数。
*   哈希表类实现了 *IDictionary* 、 *ICollection* 、 *IEnumerable* 、 *ISerializable* 、 *IDeserializationCallback* 和*I colloneable*接口。
*   在哈希表中，可以存储相同类型和不同类型的元素。
*   哈希表中作为键/值对的元素存储在字典条目中，因此您也可以将键/值对转换为*字典条目*。
*   在哈希表中，键必须是唯一的。不允许重复的键。

#### 如何创建哈希表？

哈希表类提供了 **16** 种不同类型的构造函数用来创建一个哈希表，这里我们只使用*哈希表()构造函数*。要了解更多关于哈希表的构造函数，你可以参考 [**C# |哈希表类**](https://www.geeksforgeeks.org/c-sharp-hashtable-class/) 这个构造函数用来创建一个哈希表类的实例，这个实例是空的，并且有默认的初始容量、加载因子、哈希代码提供者和比较器。现在，让我们看看如何使用 hashtable()构造函数创建哈希表:

**第一步:**包含系统。借助使用关键字的*在程序中收集命名空间:*

```cs
using System.Collections;
```

**步骤 2:** 使用哈希表类创建哈希表，如下所示:

```cs
Hashtable hashtable_name = new Hashtable();
```

**第三步:**如果想要在哈希表中添加一个键/值对，那么使用 add()方法在哈希表中添加元素。您也可以在哈希表中存储一个键/值对，而无需使用 [Add()方法](https://www.geeksforgeeks.org/c-adding-an-element-into-the-hashtable/)。

**示例:**

## C#

```cs
// C# program to illustrate how
// to create a hashtable
using System;
using System.Collections;

class GFG {

    // Main Method
    static public void Main()
    {

        // Create a hashtable
        // Using Hashtable class
        Hashtable my_hashtable1 = new Hashtable();

        // Adding key/value pair
        // in the hashtable
        // Using Add() method
        my_hashtable1.Add("A1", "Welcome");
        my_hashtable1.Add("A2", "to");
        my_hashtable1.Add("A3", "GeeksforGeeks");

        Console.WriteLine("Key and Value pairs from my_hashtable1:");

        foreach(DictionaryEntry ele1 in my_hashtable1)
        {
            Console.WriteLine("{0} and {1} ", ele1.Key, ele1.Value);
        }

        // Create another hashtable
        // Using Hashtable class
        // and adding key/value pairs
        // without using Add method
        Hashtable my_hashtable2 = new Hashtable() {
                                      {1, "hello"},
                                          {2, 234},
                                        {3, 230.45},
                                         {4, null}};

        Console.WriteLine("Key and Value pairs from my_hashtable2:");

        foreach(var ele2 in my_hashtable2.Keys)
        {
            Console.WriteLine("{0}and {1}", ele2,
                            my_hashtable2[ele2]);
        }
    }
}
```

**Output:** 

```cs
Key and Value pairs from my_hashtable1:
A3 and GeeksforGeeks 
A2 and to 
A1 and Welcome 
Key and Value pairs from my_hashtable2:
4and 
3and 230.45
2and 234
1and hello
```

#### 如何从哈希表中移除元素？

在哈希表中，您可以从哈希表中移除元素。哈希表类提供了两种不同的方法来移除元素，这两种方法是:

*   [**清除**](https://www.geeksforgeeks.org/c-remove-all-elements-from-the-hashtable/) **:** 此方法用于移除散列表中的所有对象。
*   [**移除**](https://www.geeksforgeeks.org/c-remove-the-element-with-the-specified-key-from-the-hashtable/) **:** 此方法用于从哈希表中移除具有指定键的元素。

**示例:**

## C#

```cs
// C# program to illustrate how
// remove elements from the hashtable
using System;
using System.Collections;

class GFG {

    // Main Method
    static public void Main()
    {

        // Create a hashtable
        // Using Hashtable class
        Hashtable my_hashtable = new Hashtable();

        // Adding key/value pair
        // in the hashtable
        // Using Add() method
        my_hashtable.Add("A1", "Welcome");
        my_hashtable.Add("A2", "to");
        my_hashtable.Add("A3", "GeeksforGeeks");

        // Using remove method
        // remove A2 key/value pair
        my_hashtable.Remove("A2");

        Console.WriteLine("Key and Value pairs :");

        foreach(DictionaryEntry ele1 in my_hashtable)
        {
            Console.WriteLine("{0} and {1} ", ele1.Key, ele1.Value);
        }

        // Before using Clear method
        Console.WriteLine("Total number of elements present"+
                 " in my_hashtable:{0}", my_hashtable.Count);

        my_hashtable.Clear();

        // After using Clear method
        Console.WriteLine("Total number of elements present in"+
                       " my_hashtable:{0}", my_hashtable.Count);
    }
}
```

**Output:** 

```cs
Key and Value pairs :
A3 and GeeksforGeeks 
A1 and Welcome 
Total number of elements present in my_hashtable:2
Total number of elements present in my_hashtable:0
```

#### 如何检查哈希表中键/值对的可用性？

在哈希表中，可以使用以下方法检查给定的对是否存在:

*   [**包含**](https://www.geeksforgeeks.org/c-check-whether-a-hashtable-contains-a-specific-key-or-not/) **:** 此方法用于检查哈希表是否包含特定的键。
*   [**【contains key】**](https://www.geeksforgeeks.org/c-check-if-the-hashtable-contains-a-specific-key/)**:**这个方法也用来检查哈希表是否包含特定的键。
*   [**contains value**](https://www.geeksforgeeks.org/c-check-if-the-hashtable-contains-a-specific-value/)**:**此方法用于检查哈希表是否包含特定值。

**示例:**

## C#

```cs
// C# program to illustrate how
// to check key/value present
// in the hashtable or not
using System;
using System.Collections;

class GFG {

    // Main Method
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

        // Determine whether the given
        // key present or not
        // using Contains method
        Console.WriteLine(my_hashtable.Contains("A3"));
        Console.WriteLine(my_hashtable.Contains(12));
        Console.WriteLine();

        // Determine whether the given
        // key present or not
        // using ContainsKey method
        Console.WriteLine(my_hashtable.ContainsKey("A1"));
        Console.WriteLine(my_hashtable.ContainsKey(1));
        Console.WriteLine();

        // Determine whether the given
        // value present or not
        // using ContainsValue method
        Console.WriteLine(my_hashtable.ContainsValue("geeks"));
        Console.WriteLine(my_hashtable.ContainsValue("to"));
    }
}
```

**Output:** 

```cs
True
False

True
False

False
True
```