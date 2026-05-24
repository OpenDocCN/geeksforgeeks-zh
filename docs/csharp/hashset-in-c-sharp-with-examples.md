# C # 中的哈希集，带示例

> 原文:[https://www . geesforgeks . org/hashset-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/hashset-in-c-sharp-with-examples/)

在 C# 中，HashSet 是唯一元素的无序集合。本集在*中介绍。NET 3.5* 。它支持集合的实现，并使用哈希表进行存储。该集合属于泛型集合，在*系统下定义。集合.通用*命名空间。当我们想要防止集合中放置重复的元素时，通常会使用它。与列表相比，HashSet 的性能要好得多。

**要点:**

*   HashSet 类实现了 *ICollection* 、 *IEnumerable* 、*ireadonlyccollection*、 *ISet* 、 *IEnumerable* 、*IDeserializationCallback*和 *ISerializable* 接口。
*   在 HashSet 中，元素的顺序没有定义。您不能对 HashSet 的元素进行排序。
*   在 HashSet 中，元素必须是唯一的。
*   在 HashSet 中，不允许有重复的元素。
*   Is 提供了许多数学集合运算，如交集、并集和差集。
*   HashSet 的容量是它可以容纳的元素数量。
*   哈希集是一个动态集合，这意味着当添加新元素时，哈希集的大小会自动增加。
*   在 HashSet 中，只能存储相同类型的元素。

#### 如何创建一个 HashSet？

HashSet 类提供了 *7 种不同类型的构造函数*，用来创建一个 HashSet，这里我们只使用 *HashSet()* ，构造函数。要了解更多关于 HashSet 的构造函数，可以参考[T5】c# | HashSet 类 T7。](https://www.geeksforgeeks.org/c-sharp-hashset-class/)

**HashSet():** 用于创建 HashSet 类的一个实例，该实例为空，并使用集合类型的默认相等比较器。

**第一步:**包含*系统。集合。通用*命名空间在您的程序中借助*使用*关键字:

```cs
using System.Collections.Generic;
```

**步骤 2:** 使用 HashSet 类创建 HashSet，如下所示:

```cs
HashSet<Type_of_hashset> Hashset_name = new HashSet<Type_of_hashset>(); 
```

**第三步:**如果你想在你的 HashSet 中添加元素，那么使用 *Add()* 方法在你的 HashSet 中添加元素。您还可以使用集合初始值设定项将元素存储在 HashSet 中。

**步骤 4:** 通过使用 *foreach* 循环访问 HashSet 的元素。如下例所示。

**示例:**

## C#

```cs
// C# program to illustrate how to
// create hashset
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating HashSet
        // Using HashSet class
        HashSet<string> myhash1 = new HashSet<string>();

        // Add the elements in HashSet
        // Using Add method
        myhash1.Add("C");
        myhash1.Add("C++");
        myhash1.Add("C#");
        myhash1.Add("Java");
        myhash1.Add("Ruby");
        Console.WriteLine("Elements of myhash1:");

        // Accessing elements of HashSet
        // Using foreach loop
        foreach(var val in myhash1)
        {
            Console.WriteLine(val);
        }

        // Creating another HashSet
        // using collection initializer
        // to initialize HashSet
        HashSet<int> myhash2 = new HashSet<int>() {10,
                               100,1000,10000,100000};

        // Display elements of myhash2
        Console.WriteLine("Elements of myhash2:");
        foreach(var value in myhash2)
        {
            Console.WriteLine(value);
        }
    }
}
```

**Output:** 

```cs
Elements of myhash1:
C
C++
C#
Java
Ruby
Elements of myhash2:
10
100
1000
10000
100000
```

#### 如何从 HashSet 中移除元素？

在哈希集中，您可以从哈希集中移除元素。HashSet <t>类提供了三种不同的方法来移除元素，这些方法是:</t>

*   [**【移除(T)**](https://www.geeksforgeeks.org/c-remove-the-specified-element-from-a-hashset/) **:** 此方法用于从 HashSet 对象中移除指定的元素。
*   [**移除 Where(谓词)**](https://www.geeksforgeeks.org/c-remove-elements-from-a-hashset-with-conditions-defined-by-the-predicate/) **:** 此方法用于从 HashSet 集合中移除所有与指定谓词定义的条件相匹配的元素。
*   [**清除**](https://www.geeksforgeeks.org/c-remove-all-elements-from-a-hashset/) **:** 此方法用于从一个 HashSet 对象中移除所有元素。

**例 1:**

## C#

```cs
// C# program to illustrate how to
// remove elements of HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating HashSet
        // Using HashSet class
        HashSet<string> myhash = new HashSet<string>();

        // Add the elements in HashSet
        // Using Add method
        myhash.Add("C");
        myhash.Add("C++");
        myhash.Add("C#");
        myhash.Add("Java");
        myhash.Add("Ruby");

        // Before using Remove method
        Console.WriteLine("Total number of elements present (Before Removal)"+
                            " in myhash: {0}", myhash.Count);

        // Remove element from HashSet
        // Using Remove method
        myhash.Remove("Ruby");

        // After using Remove method
        Console.WriteLine("Total number of elements present (After Removal)"+
                            " in myhash: {0}", myhash.Count);

        // Remove all elements from HashSet
        // Using Clear method
        myhash.Clear();
        Console.WriteLine("Total number of elements present"+
                             " in myhash:{0}", myhash.Count);
    }
}
```

**Output:** 

```cs
Total number of elements present in myhash: 5
Total number of elements present in myhash: 4
Total number of elements present in myhash:0
```

#### 设置操作

HashSet 类还提供了一些用于对集合执行不同操作的方法，这些方法是:

*   [**【union with(IEnumerable)**](https://www.geeksforgeeks.org/c-union-of-two-hashset/)**:**此方法用于修改当前 HashSet 对象以包含其自身、指定集合或两者中存在的所有元素。
    **例:**

## C#

```cs
// C# program to illustrate set operations
using System;
using System.Collections.Generic;

class GFG {

    static public void Main()
    {

        // Creating HashSet
        // Using HashSet class
        HashSet<string> myhash1 = new HashSet<string>();

        // Add the elements in HashSet
        // Using Add method
        myhash1.Add("C");
        myhash1.Add("C++");
        myhash1.Add("C#");
        myhash1.Add("Java");
        myhash1.Add("Ruby");

        // Creating another HashSet
        // Using HashSet class
        HashSet<string> myhash2 = new HashSet<string>();

        // Add the elements in HashSet
        // Using Add method
        myhash2.Add("PHP");
        myhash2.Add("C++");
        myhash2.Add("Perl");
        myhash2.Add("Java");

        // Using UnionWith method
        myhash1.UnionWith(myhash2);
        foreach(var ele in myhash1)
        {
            Console.WriteLine(ele);
        }
    }
}
```

**Output:** 

```cs
C
C++
C#
Java
Ruby
PHP
Perl
```

*   [**【intersecwith(IEnumerable)**](https://www.geeksforgeeks.org/c-intersection-of-two-hashsets/)**:**此方法用于修改当前 HashSet 对象，使其仅包含该对象和指定集合中存在的元素。
    **例:**

## C#

```cs
// C# program to illustrate set operations
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating HashSet
        // Using HashSet class
        HashSet<string> myhash1 = new HashSet<string>();

        // Add the elements in HashSet
        // Using Add method
        myhash1.Add("C");
        myhash1.Add("C++");
        myhash1.Add("C#");
        myhash1.Add("Java");
        myhash1.Add("Ruby");

        // Creating another HashSet
        // Using HashSet class
        HashSet<string> myhash2 = new HashSet<string>();

        // Add the elements in HashSet
        // Using Add method
        myhash2.Add("PHP");
        myhash2.Add("C++");
        myhash2.Add("Perl");
        myhash2.Add("Java");

        // Using IntersectWith method
        myhash1.IntersectWith(myhash2);
        foreach(var ele in myhash1)
        {
            Console.WriteLine(ele);
        }
    }
}
```

**Output:** 

```cs
C++
Java
```

*   [**except with(IEnumerable)**](https://www.geeksforgeeks.org/c-remove-all-elements-in-a-collection-from-a-hashset/)**:**此方法用于从当前 HashSet 对象中移除指定集合中的所有元素。
    **例:**

## C#

```cs
// C# program to illustrate set operations
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating HashSet
        // Using HashSet class
        HashSet<string> myhash1 = new HashSet<string>();

        // Add the elements in HashSet
        // Using Add method
        myhash1.Add("C");
        myhash1.Add("C++");
        myhash1.Add("C#");
        myhash1.Add("Java");
        myhash1.Add("Ruby");

        // Creating another HashSet
        // Using HashSet class
        HashSet<string> myhash2 = new HashSet<string>();

        // Add the elements in HashSet
        // Using Add method
        myhash2.Add("PHP");
        myhash2.Add("C++");
        myhash2.Add("Perl");
        myhash2.Add("Java");

        // Using ExceptWith method
        myhash1.ExceptWith(myhash2);
        foreach(var ele in myhash1)
        {
            Console.WriteLine(ele);
        }
    }
}
```

**Output:** 

```cs
C
C#
Ruby
```