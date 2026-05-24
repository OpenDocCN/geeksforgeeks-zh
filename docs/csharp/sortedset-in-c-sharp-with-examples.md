# 用例子在 C# 中排序集合

> 原文:[https://www . geeksforgeeks . org/sorted set-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/sortedset-in-c-sharp-with-examples/)

在 C# 中，SortedSet 是按排序顺序排列的对象的集合。属于泛型集合，在**系统下定义。集合.通用**命名空间。它还提供了许多数学集合运算，如交集、并集和差集。这是一个动态集合，意味着当添加新元素时，SortedSet 的大小会自动增加。
**要点:**

*   SortedSet 类实现了 *ICollection* 、 *IEnumerable* 、*ireadonlyccollection*、 *ISet* 、 *ICollection* 、 *IEnumerable* 、*IDeserializationCallback*、 *ISerializable* 接口。
*   SortedSet 的容量是它可以容纳的元素数量。
*   在排序集中，元素必须是唯一的。
*   在 SortedSet 中，元素的顺序是升序。
*   如果您必须存储唯一的元素并保持升序，则通常在我们想要使用 SortedSet 类时使用它。
*   在 SortedSet 中，用户只能存储相同类型的元素。

#### 如何创建 SortedSet？

SortedSet 类提供了 5 种不同类型的构造函数，用来创建一个 SortedSet，这里我们只使用 *SortedSet()* ，构造函数。要了解更多关于 SortedSet 的构造函数，可以参考 [**C# | SortedSet 类**](https://www.geeksforgeeks.org/c-sharp-sortedset-class/) 。
**SortedSet():** 用于创建 SortedSet 类的实例。
**第一步:**包含*系统。集合。借助于使用*关键字:
的*在程序中的通用*命名空间

> 使用系统。集合。通用；

**步骤 2:** 使用 SortedSet 类创建一个 SortedSet，如下所示:

> 排序集<type_of_sortedset>排序集 _name =新排序集<type_of_sortedset>()；</type_of_sortedset></type_of_sortedset>

**第三步:**如果要在排序集中添加元素，那么使用 *Add()* 方法在排序集中添加元素。您还可以使用集合初始值设定项在 SortedSet 中存储元素。
**第四步:**sorted set 的元素通过 foreach 循环访问。如下例所示。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to
// create SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver Class
    static public void Main()
    {

        // Creating SortedSet
        // Using SortedSet class
        SortedSet<int> my_Set1 = new SortedSet<int>();

        // Add the elements in SortedSet
        // Using Add method
        my_Set1.Add(101);
        my_Set1.Add(1001);
        my_Set1.Add(10001);
        my_Set1.Add(100001);
        Console.WriteLine("Elements of my_Set1:");

        // Accessing elements of SortedSet
        // Using foreach loop
        foreach(var val in my_Set1)
        {
            Console.WriteLine(val);
        }

        // Creating another SortedSet
        // using collection initializer
        // to initialize SortedSet
        SortedSet<int> my_Set2 = new SortedSet<int>() {
                                202,2002,20002,200002};

        // Display elements of my_Set2
        Console.WriteLine("Elements of my_Set2:");
        foreach(var value in my_Set2)
        {
            Console.WriteLine(value);
        }
    }
}
```

**Output:** 

```cs
Elements of my_Set1:
101
1001
10001
100001
Elements of my_Set2:
202
2002
20002
200002
```

#### 如何从 SortedSet 中移除元素？

在排序集中，您可以从排序集中移除元素。SortedSet <t>类提供了三种不同的方法来移除元素，这些方法是:</t> 

*   [**【移除(T)**](https://www.geeksforgeeks.org/c-remove-a-specified-item-from-sortedset/) **:** 此方法用于从排序集中移除指定的项目。
*   [**移除 Where(谓词):**](https://www.geeksforgeeks.org/c-remove-elements-from-a-sortedset-that-match-the-predicate/) 此方法用于从 SortedSet 中移除与指定谓词定义的条件相匹配的所有元素。
*   [**【清除()】**](https://www.geeksforgeeks.org/c-remove-all-elements-from-the-sortedset/) **:** 此方法用于从集合中移除所有元素。

**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to
// remove elements from SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating SortedSet
        // Using SortedSet class
        SortedSet<int> my_Set = new SortedSet<int>();

        // Add the elements in SortedSet
        // Using Add method
        my_Set.Add(101);
        my_Set.Add(1001);
        my_Set.Add(10001);
        my_Set.Add(100001);

        // After using Remove method
        Console.WriteLine("Total number of elements "+
               "present in my_Set:{0}", my_Set.Count);

        // Remove element from SortedSet
        // Using Remove method
        my_Set.Remove(1001);

        // Before using Remove method
        Console.WriteLine("Total number of elements "+
               "present in my_Set:{0}", my_Set.Count);

        // Remove all elements from SortedSet
        // Using Clear method
        my_Set.Clear();
        Console.WriteLine("Total number of elements "+
               "present in my_Set:{0}", my_Set.Count);
    }
}
```

**Output:** 

```cs
Total number of elements present in my_Set:4
Total number of elements present in my_Set:3
Total number of elements present in my_Set:0
```

#### 如何检查 SortedSet 中元素的可用性？

在 SortedSet 中，可以使用 [Contains](https://www.geeksforgeeks.org/c-check-if-the-sortedset-contains-a-specific-element/) 方法检查给定元素是否存在。此方法用于确定集合是否包含特定元素。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to check
// availability of elements in SortedSet
using System;
using System.Collections.Generic;

public class GFG {
    static public void Main()
    {

        // Creating SortedSet
        // Using SortedSet class
        SortedSet<int> my_Set = new SortedSet<int>();

        // Add the elements in SortedSet
        // Using Add method
        my_Set.Add(101);
        my_Set.Add(1001);
        my_Set.Add(10001);
        my_Set.Add(100001);

        // Check the given element present
        // in the SortedSet or not
        // Using Contains method
        if (my_Set.Contains(101) == true)
        {
            Console.WriteLine("Element is available..!");
        }

        else
        {
            Console.WriteLine("Element is not available..!");
        }
    }
}
```

**Output:** 

```cs
Element is available..!
```