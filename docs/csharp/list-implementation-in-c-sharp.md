# c# 中的列表实现

> 原文:[https://www . geesforgeks . org/list-implementation-in-c-sharp/](https://www.geeksforgeeks.org/list-implementation-in-c-sharp/)

在 C# 中，**列表**是一个通用集合，用于以列表的形式存储元素或对象，它是在*系统下定义的。集合.泛型*命名空间。它提供了与[数组列表](https://www.geeksforgeeks.org/arraylist-in-c-sharp/)相同的功能，但是只有一个区别，即列表是通用的，而数组列表是非通用的集合。它本质上是动态的，意味着列表的大小会根据需要而增长。

**要点:**

*   List 类实现了 icocollection<t>、IEnumerable <t>、IList <t>、ireadonlyccollection<t>、IReadOnlyList <t>、icocollection、IEnumerable 和 IList 接口。</t></t></t></t></t>
*   它可以接受 null 作为引用类型的有效值，也允许重复元素。
*   如果计数等于容量，则列表的容量会通过重新分配内部阵列而自动增加。在添加新元素之前，现有元素将被复制到新数组中。
*   默认情况下，列表中的元素不排序，元素由从零开始的索引访问。

#### 如何创建列表？

一个列表类有 3 个构造函数，用于创建一个列表，构造函数如下:

*   **List < T > ():** 此构造函数用于创建 List < T >类的一个实例，该实例为空并且具有默认的初始容量。
*   **List<T>(IEnumerable):**此构造函数用于创建 List < T >类的实例，该实例包含从指定集合复制的元素，并且具有足够的容量来容纳复制的元素数量。
*   **List < T > (Int32):** 此构造函数用于创建 List < T >类的一个实例，该实例为空并且具有指定的初始容量。

我们来看看如何使用 *List < T >()构造函数*创建列表:

**第一步:**包含系统。集合。通过使用关键字，在您的程序中借助*的泛型命名空间。*

```cs
using System.Collections.Generic;
```

**步骤 2:** 使用列表< T >类创建列表，如下所示:

```cs
List list_name = new List(); 
```

**第三步:**如果要在列表中添加元素，那么 List < T >类提供了*两种*不同的方法，方法是:

*   [**添加(T)**](https://www.geeksforgeeks.org/c-adding-an-element-to-the-list/) **:** 此方法用于将一个对象添加到列表的末尾< T >。
*   [**添加范围(IEnumerable)<T>)**](https://www.geeksforgeeks.org/c-adding-the-elements-of-the-specified-collection-to-the-end-of-the-list/)**:**此方法用于将指定集合的元素添加到列表< T >的末尾。

**注意:**也可以使用集合初始值设定项添加元素。如下例所示:

**示例:**

> //使用 List 类
> //创建列表并使用
> //集合初始值设定项
> List <字符串> my_list1 =新列表<字符串> () {“极客”、“极客 123”、“极客 forgeeks”}；

**第四步:**可以通过以下方式访问列表的元素:

*   **使用 foreach 循环:**可以使用 foreach 循环访问列表的元素/对象。
    T3】例:

> //访问 my_list
> //使用 foreach 循环
> foreach(my _ list 中的 int a)
> {
> 控制台。write line(a)；
> }

*   **使用 ForEach()方法:**该方法用于对*列表< T >* 的每个元素执行指定的动作。
    **例:**

> //访问 my_list 的元素
> //使用 ForEach 方法
> my_list。ForEach(a = >控制台。write line(a))；

*   **使用 for 循环:**可以使用 for 循环访问列表的元素/对象。
    T3】例:

> //访问 my_list
> 的元素//使用 for 循环
> for(int a = 0；a <我的 _ 清单。计数；a++)
> {
> 控制台。write line(my _ list[a])；
> }

*   **使用索引器:**可以使用索引器访问列表的元素/对象。
    T3】例:

> //访问 my_list 的元素
> //使用索引器
> 控制台。write line(my _ list[3])；
> 控制台。write line(my _ list[4])；

**示例:**

## C#

```cs
// C# program to illustrate how
// to create a list
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating list using List class
        // and List<T>() Constructor
        List<int> my_list = new List<int>();

        // Adding elements to List
        // Using Add() method
        my_list.Add(1);
        my_list.Add(10);
        my_list.Add(100);
        my_list.Add(1000);
        my_list.Add(10000);
        my_list.Add(100000);
        my_list.Add(1000000);

        // Accessing elements of my_list
        // Using foreach loop
        foreach(int a in my_list)
        {
            Console.WriteLine(a);
        }
    }
}
```

**Output:** 

```cs
1
10
100
1000
10000
100000
1000000
```

#### 如何从列表中删除元素？

您可以使用列表<t>类提供的以下方法删除列表中的元素:</t>

*   [**【移除(T)**](https://www.geeksforgeeks.org/c-removing-the-specified-element-from-the-list/) **:** 此方法用于从列表中移除特定对象的第一次出现。
*   [**RemoveAll(谓词< T > )**](https://www.geeksforgeeks.org/c-remove-all-elements-of-a-list-that-match-the-conditions-defined-by-the-predicate/) **:** 此方法用于移除与指定谓词定义的条件相匹配的所有元素。
*   [**【移除 At(Int32)**](https://www.geeksforgeeks.org/c-how-to-remove-the-element-from-the-specified-index-of-the-list/) **:** 此方法用于移除列表中指定索引处的元素。
*   [**移除范围(Int32，Int32)**](https://www.geeksforgeeks.org/c-removing-a-range-of-elements-from-the-list/) **:** 此方法用于从列表< T >中移除一系列元素。
*   [**【清除】(**](https://www.geeksforgeeks.org/c-removing-all-the-elements-from-the-list/) **:** 此方法用于从列表< T >中移除所有元素。

**示例:**

## C#

```cs
// C# program to illustrate how
// to remove objects from the list
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating list using List class
        // and List<T>() Constructor
        List<int> my_list = new List<int>();

        // Adding elements to List
        // Using Add() method
        my_list.Add(1);
        my_list.Add(10);
        my_list.Add(100);
        my_list.Add(1000);
        my_list.Add(10000);
        my_list.Add(100000);
        my_list.Add(1000000);
        my_list.Add(10000000);
        my_list.Add(100000000);

        // Initial count
        Console.WriteLine("Initial count:{0}", my_list.Count);

        // After using Remove() method
        my_list.Remove(10);
        Console.WriteLine("2nd count:{0}", my_list.Count);

        // After using RemoveAt() method
        my_list.RemoveAt(4);
        Console.WriteLine("3rd count:{0}", my_list.Count);

        // After using RemoveRange() method
        my_list.RemoveRange(0, 2);
        Console.WriteLine("4th count:{0}", my_list.Count);

        // After using Clear() method
        my_list.Clear();
        Console.WriteLine("5th count:{0}", my_list.Count);
    }
}
```

**Output:** 

```cs
Initial count:9
2nd count:8
3rd count:7
4th count:5
5th count:0
```

#### 如何对列表进行排序？

您可以使用 sort()方法对元素进行排序。此方法用于使用指定或默认的 IComparer <t>实现或提供的比较<t>委托来比较列表元素，对列表<t>中的元素或部分元素进行排序。</t></t></t>

**示例:**

## C#

```cs
// C# program to illustrate how
// sort a list
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating list using List class
        // and List<T>() Constructor
        List<int> my_list = new List<int>();

        // Adding elements to List
        // Using Add() method
        my_list.Add(496);
        my_list.Add(1000);
        my_list.Add(100);
        my_list.Add(10);
        my_list.Add(10000);
        my_list.Add(10000000);
        my_list.Add(1000000);
        my_list.Add(100000);
        my_list.Add(0000);

        // Without sorted List
        Console.WriteLine("UnSorted List:");
        foreach(int a in my_list)
        {
            Console.WriteLine(a);
        }

        // After Sort method
        my_list.Sort();
        Console.WriteLine("Sorted List:");
        foreach(int a in my_list)
        {
            Console.WriteLine(a);
        }
    }
}
```

**Output:** 

```cs
UnSorted List:
496
1000
100
10
10000
10000000
1000000
100000
0
Sorted List:
0
10
100
496
1000
10000
100000
1000000
10000000
```