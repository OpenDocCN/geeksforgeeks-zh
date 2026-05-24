# C# 排序列表及示例

> 原文:[https://www . geeksforgeeks . org/c-sharp-sorted list-with-examples/](https://www.geeksforgeeks.org/c-sharp-sortedlist-with-examples/)

在 C# 中，SortedList 是根据键排序的键/值对的集合。默认情况下，此集合按升序对键/值对进行排序。它是泛型和非泛型集合类型。通用排序列表在系统中定义。集合。通用命名空间，而非通用排序列表在系统下定义。集合命名空间，这里我们将讨论非泛型类型 SortedList。
**要点:**

*   SortedList 类实现了 *IEnumerable* 、 *ICollection* 、 *IDictionary* 和*I lonely*接口。
*   在 SortedList 中，可以通过元素的键或索引来访问元素。
*   SortedList 对象在内部维护两个数组来存储列表元素，即一个数组用于键，另一个数组用于关联值。
*   这里，键不能为空，但值可以为空。
*   SortedList 对象的容量是它可以容纳的键/值对的数量。
*   在排序列表中，不允许重复键。
*   在 SortedList 中，由于非泛型集合，您可以存储相同类型和不同类型的值。如果在程序中使用通用排序列表，那么值的类型必须相同。
*   在 SortedList 中，不能在同一个 SortedList 中存储不同数据类型的键，因为编译器会抛出异常。因此，总是在相同类型的排序列表中添加关键字。
*   您也可以将 SortedList 的键/值对转换为 DictionaryEntry。

#### 如何创建排序列表？

SortedList 类提供了 **6** 种不同类型的构造函数，用于创建 SortedList，这里我们只使用 SortedList()，构造函数。要了解更多关于 SortedList 的构造函数，可以参考[T3】c# | sorted list 类 T5。
**SortedList():** 用于创建 SortedList 类的一个实例，该实例为空，具有默认的初始容量，并根据添加到 SortedList 对象的每个键实现的 IComparable 接口进行排序。
**第一步:**包含系统。在你的程序中借助集合命名空间使用关键字:](https://www.geeksforgeeks.org/c-sharp-sortedlist-class/) 

```cs
using System.Collections;
```

**步骤 2:** 使用 SortedList 类创建一个 SortedList，如下所示:

```cs
SortedList list_name = new SortedList();
```

**第三步:**如果要在排序列表中添加一个键/值对，那么使用 [Add()方法](https://www.geeksforgeeks.org/c-how-to-add-key-value-pairs-in-sortedlist/)在排序列表中添加键/值对。您还可以在 SortedList 中存储一个键/值对，而无需使用 Add()方法，这种语法被称为集合初始值设定项语法，如下例所示。
**步骤 4:** 使用**三种不同的方式访问排序列表的键/值对:** 

*   **for 循环:**您可以使用 for 循环来访问 SortedList 的键/值对。
    **例:**

## c sharp . c sharp . c sharp . c sharp

```cs
for (int x = 0; x < my_slist1.Count; x++)
{
    Console.WriteLine("{0} and {1}",
                my_slist1.GetKey(x),
           my_slist1.GetByIndex(x));
}
```

*   **使用索引:**您可以使用索引访问 SortedList 的单个值。您需要将键或索引作为参数传递，以找到相应的值。如果指定的键不可用，编译器将抛出一个错误。
    **例:**

## c sharp . c sharp . c sharp . c sharp

```cs
Console.WriteLine("Value is:{0}", my_slist1[1.04]);

string x = (string)my_slist[1.02];

Console.WriteLine(x);
```

*   **foreach 循环:**可以使用 foreach 循环访问 SortedList 的键/值对。
    **例:**

## c sharp . c sharp . c sharp . c sharp

```cs
foreach(DictionaryEntry pair in my_slist1)
{
    Console.WriteLine("{0} and {1}",
              pair.Key, pair.Value);
}
```

**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how
// to create a sortedlist
using System;
using System.Collections;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating a sortedlist
        // Using SortedList class
        SortedList my_slist1 = new SortedList();

        // Adding key/value pairs in
        // SortedList using Add() method
        my_slist1.Add(1.02, "This");
        my_slist1.Add(1.07, "Is");
        my_slist1.Add(1.04, "SortedList");
        my_slist1.Add(1.01, "Tutorial");

        foreach(DictionaryEntry pair in my_slist1)
        {
            Console.WriteLine("{0} and {1}",
                      pair.Key, pair.Value);
        }
        Console.WriteLine();

        // Creating another SortedList
        // using Object Initializer Syntax
        // to initialize sortedlist
        SortedList my_slist2 = new SortedList() {
                                  { "b.09", 234 },
                                  { "b.11", 395 },
                                  { "b.01", 405 },
                                  { "b.67", 100 }};

        foreach(DictionaryEntry pair in my_slist2)
        {
            Console.WriteLine("{0} and {1}",
                      pair.Key, pair.Value);
        }
    }
}
```

**Output:** 

```cs
1.01 and Tutorial
1.02 and This
1.04 and SortedList
1.07 and Is

b.01 and 405
b.09 and 234
b.11 and 395
b.67 and 100
```

#### 如何从 SortedList 中移除元素？

*   [**清除**](https://www.geeksforgeeks.org/c-remove-all-elements-from-a-sortedlist/) **:** 此方法用于移除排序列表对象中的所有元素。
*   [**移除**](https://www.geeksforgeeks.org/c-sharp-remove-the-element-with-the-specified-key-from-a-sortedlist/) **:** 此方法用于从 SortedList 对象中移除具有指定键的元素。
*   [**移除**](https://www.geeksforgeeks.org/c-sharp-remove-from-the-specified-index-of-a-sortedlist/) **:** 此方法用于移除排序列表对象的指定索引处的元素。

**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to
// remove key/value pairs from
// the sortedlist
using System;
using System.Collections;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating a sortedlist
        // Using SortedList class
        SortedList my_slist = new SortedList();

        // Adding key/value pairs in SortedList
        // Using Add() method
        my_slist.Add(1.02, "This");
        my_slist.Add(1.07, "Is");
        my_slist.Add(1.04, "SortedList");
        my_slist.Add(1.01, "Tutorial");

        foreach(DictionaryEntry pair in my_slist)
        {
            Console.WriteLine("{0} and {1}",
                      pair.Key, pair.Value);
        }
        Console.WriteLine();

        // Remove value having 1.07 key
        // Using Remove() method
        my_slist.Remove(1.07);

        // After Remove() method
        foreach(DictionaryEntry pair in my_slist)
        {
            Console.WriteLine("{0} and {1}",
                      pair.Key, pair.Value);
        }
        Console.WriteLine();

        // Remove element at index 2
        // Using RemoveAt() method
        my_slist.RemoveAt(2);

        // After RemoveAt() method
        foreach(DictionaryEntry pair in my_slist)
        {
            Console.WriteLine("{0} and {1}",
                      pair.Key, pair.Value);
        }
        Console.WriteLine();

        // Remove all key/value pairs
        // Using Clear method
        my_slist.Clear();
        Console.WriteLine("The total number of key/value pairs"+
                    " present in my_slist:{0}", my_slist.Count);
    }
}
```

**Output:** 

```cs
1.01 and Tutorial
1.02 and This
1.04 and SortedList
1.07 and Is

1.01 and Tutorial
1.02 and This
1.04 and SortedList

1.01 and Tutorial
1.02 and This

The total number of key/value pairs present in my_slist:0
```

#### 如何在 SortedList 中检查键/值对的可用性？

在 SortedList 中，您可以使用以下方法检查给定的对是否存在:

*   [**包含**](https://www.geeksforgeeks.org/c-check-whether-a-sortedlist-object-contains-a-specific-key/) **:** 此方法用于检查 SortedList 对象是否包含特定键。
*   [**【contains key】**](https://www.geeksforgeeks.org/c-sharp-search-in-a-sortedlist-object/)**:**此方法用于检查 SortedList 对象是否包含特定的键。
*   [**contains value**](https://www.geeksforgeeks.org/c-check-if-a-sortedlist-object-contains-a-specific-value/)**:**此方法用于检查 SortedList 对象是否包含特定值。

**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to
// check the given key or value
// present in the sortedlist or not
using System;
using System.Collections;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating a sortedlist
        // Using SortedList class
        SortedList my_slist = new SortedList();

        // Adding key/value pairs in
        // SortedList using Add() method
        my_slist.Add(1.02, "This");
        my_slist.Add(1.07, "Is");
        my_slist.Add(1.04, "SortedList");
        my_slist.Add(1.01, "Tutorial");

        // Using Contains() method to check
        // the specified key is present or not
        if (my_slist.Contains(1.02) == true)
        {
            Console.WriteLine("Key is found...!!");
        }

        else
        {
            Console.WriteLine("Key is not found...!!");
        }

        // Using ContainsKey() method to check
        // the specified key is present or not
        if (my_slist.ContainsKey(1.03) == true)
        {
            Console.WriteLine("Key is found...!!");
        }
        else
        {
            Console.WriteLine("Key is not found...!!");
        }

        // Using ContainsValue() method to check
        // the specified value is present or not
        if (my_slist.ContainsValue("Is") == true)
        {
            Console.WriteLine("Value is found...!!");
        }

        else
        {
            Console.WriteLine("Value is not found...!!");
        }
    }
}
```

**Output:** 

```cs
Key is found...!!
Key is not found...!!
Value is found...!!
```