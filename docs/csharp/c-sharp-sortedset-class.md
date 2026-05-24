# C# |排序集合类

> 原文:[https://www.geeksforgeeks.org/c-sharp-sortedset-class/](https://www.geeksforgeeks.org/c-sharp-sortedset-class/)

**SortedSet** 类表示按排序顺序排列的对象集合。这个班隶属于*T3 系统。集合.通用*命名空间。

**特征:**

*   在 C# 中，SortedSet 类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用 SortedSet 类。

#### 构造器

| 构造器 | 描述 |
| **[【sort dset()](https://www.geeksforgeeks.org/c-how-to-create-a-sortedset/)** | 初始化 SortedSet 类的新实例。 |
| **排序统计(icmparer)** | 初始化使用指定比较器的 SortedSet 类的新实例。 |
| **sort dset(无数)** | 初始化 SortedSet 类的新实例，该类包含从指定的可枚举集合中复制的元素。 |
| **排序统计(不计其数，消失)** | 初始化 SortedSet 类的新实例，该类包含从指定的可枚举集合复制的元素，并使用指定的比较器。 |
| **排序集(序列化信息，流上下文)** | 初始化包含序列化数据的 SortedSet 类的新实例。 |

**示例:**

```cs
// C# code to create a SortedSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet = new SortedSet<int>();

        // Adding elements in mySortedSet
        for (int i = 1; i <= 6; i++) {
            mySortedSet.Add(2 * i + 1);
        }

        // Displaying elements in mySortedSet
        Console.WriteLine("The elements in mySortedSet are : ");

        // Displaying the element in mySortedSet
        foreach(int i in mySortedSet)
        {
            Console.WriteLine(i);
        }
    }
}
```

**Output:**

```cs
The elements in mySortedSet are : 
3
5
7
9
11
13

```

#### 性能

| 财产 | 描述 |
| 比较 | 获取用于对排序集中的值进行排序的 IComparer 对象。 |
| **[计数](https://www.geeksforgeeks.org/c-get-the-number-of-elements-in-the-sortedset/)** | 获取排序集中的元素数量。 |
| **[Max](https://www.geeksforgeeks.org/c-get-the-maximum-value-in-the-sortedset/)** | 获取 SortedSet 中由比较器定义的最大值。 |
| **[Min](https://www.geeksforgeeks.org/c-get-the-minimum-value-in-the-sortedset/)** | 获取排序集中由比较器定义的最小值。 |

**示例:**

```cs
// C# code to illustrate the properties
// of SortedSet<T> Class
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet = new SortedSet<int>();

        // adding elements in mySortedSet
        mySortedSet.Add(1);
        mySortedSet.Add(2);
        mySortedSet.Add(3);
        mySortedSet.Add(4);
        mySortedSet.Add(5);

        // ------ Count property ----------

        // Displaying the number of elements in
        // the SortedSet using "Count" property
        Console.WriteLine("The number of elements in mySortedSet are: "
                                                + mySortedSet.Count);

        // ---------- Min property ----------
        // Displaying the minimum value in the SortedSet
        Console.WriteLine("The minimum element in SortedSet is : "
                                                + mySortedSet.Min);
    }
}
```

**Output:**

```cs
The number of elements in mySortedSet are: 5
The minimum element in SortedSet is : 1

```

#### 方法

| 方法 | 描述 |
| **[加(T)](https://www.geeksforgeeks.org/c-add-element-to-sortedset/)** | 将元素添加到集合中，并返回一个值，该值指示元素是否已成功添加。 |
| **[晴()](https://www.geeksforgeeks.org/c-remove-all-elements-from-the-sortedset/)** | 从集合中移除所有元素。 |
| **[包含(T)](https://www.geeksforgeeks.org/c-check-if-the-sortedset-contains-a-specific-element/)** | 确定集合是否包含特定元素。 |
| **CopyTo()** | 从目标数组的开头或指定的索引处开始，将 SortedSet <t>的一部分或全部复制到兼容的一维数组中。</t> |
| **create etcompare()** | 返回一个 IEqualityComparer 对象，该对象可用于创建包含单个集合的集合。 |
| **create etcompare(iequalycompairer)** | 根据指定的比较器返回一个 IEqualityComparer 对象，该对象可用于创建包含单个集合的集合。 |
| **[等于(对象)](https://www.geeksforgeeks.org/c-check-if-two-sortedsett-objects-are-equal/)** | 确定指定的对象是否等于当前对象。 |
| **除了(IEnumerable)** | 从当前 SortedSet 对象中移除指定集合中的所有元素。 |
| **[【get 分子()](https://www.geeksforgeeks.org/c-get-an-enumerator-that-iterates-through-the-sortedset/)** | 返回遍历 SortedSet 的枚举数。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| **GetObjectData(SerializationInfo，StreamingContext)** | 实现 ISerializable 接口并返回序列化 SortedSet 对象所必须的数据。 |
| **GetType()** | 获取当前实例的类型。 |
| **[GetViewBetween(T，T)](https://www.geeksforgeeks.org/c-how-to-get-a-subset-in-a-sortedset/)** | 返回排序集中子集的视图。 |
| **[【交点(无数)](https://www.geeksforgeeks.org/c-intersection-of-sortedset-with-a-collection/)** | 修改当前的 SortedSet 对象，使其只包含也在指定集合中的元素。 |
| **[【isproperty of(无数)](https://www.geeksforgeeks.org/c-check-if-a-sortedset-object-is-a-proper-subset-of-the-specified-collection/)** | 确定 SortedSet 对象是否是指定集合的适当子集。 |
| **[【isproperty(无数)](https://www.geeksforgeeks.org/c-check-if-a-sortedset-object-is-a-proper-superset-of-the-specified-collection/)** | 确定 SortedSet 对象是否是指定集合的适当超集。 |
| **[【is substitution(无数)](https://www.geeksforgeeks.org/c-check-if-a-sortedset-is-a-subset-of-the-specified-collection/)** | 确定 SortedSet 对象是否是指定集合的子集。 |
| **[【this super setf(无数)](https://www.geeksforgeeks.org/c-check-if-a-sortedset-is-a-superset-of-the-specified-collection/)** | 确定 SortedSet 对象是否是指定集合的超集。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **on 序列化(对象)** | 实现 ISerializable 接口，并在反序列化完成时引发反序列化事件。 |
| **[重叠(IEnumerable)](https://www.geeksforgeeks.org/c-check-if-sortedset-and-a-specified-collection-share-common-elements/)** | 确定当前 SortedSet 对象和指定的集合是否共享公共元素。 |
| **[移除(T)](https://www.geeksforgeeks.org/c-remove-a-specified-item-from-sortedset/)** | 从排序集中删除指定的项目。 |
| **[移除 Where(谓词)](https://www.geeksforgeeks.org/c-remove-elements-from-a-sortedset-that-match-the-predicate/)** | 从排序集中移除与指定谓词定义的条件匹配的所有元素。 |
| **反转()** | 返回一个 IEnumerable，它以相反的顺序遍历 SortedSet。 |
| **[【setequals(无数)](https://www.geeksforgeeks.org/c-check-if-sortedset-and-the-specified-collection-contain-the-same-elements/)** | 确定当前的 SortedSet 对象和指定的集合是否包含相同的元素。 |
| **symmetrixceptwith(无数)** | 修改当前的 SortedSet 对象，使其只包含当前对象或指定集合中存在的元素，而不同时包含这两种元素。 |
| **ToString()** | 返回表示当前对象的字符串。 |
| **压力值(t，T)** | 在集合中搜索给定值，并返回它找到的相等值(如果有)。 |
| **[union with(IEnumerable)](https://www.geeksforgeeks.org/c-union-of-sortedset-to-a-collection/)** | 修改当前的 SortedSet 对象，使其包含当前对象或指定集合中存在的所有元素。 |

**示例:**

```cs
// C# code to illustrate the methods
// of SortedSet<T> Class
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a SortedSet of integers
        SortedSet<int> mySortedSet = new SortedSet<int>();

        // adding elements in mySortedSet
        mySortedSet.Add(2);
        mySortedSet.Add(4);
        mySortedSet.Add(6);
        mySortedSet.Add(8);
        mySortedSet.Add(10);

        //-------- Remove Method --------

        // Removing element "4" if found
        mySortedSet.Remove(4);

        // Displaying the elements in mySortedSet
        foreach(int i in mySortedSet)
        {
            Console.WriteLine(i);
        }

        Console.WriteLine("After Using Method");

        // Removing element "14" if found
        mySortedSet.Remove(14);

        // Displaying the element in mySortedSet
        foreach(int i in mySortedSet)
        {
            Console.WriteLine(i);
        }

        // -------- IsSubsetOf Method --------

        // Creating a SortedSet of integers
        SortedSet<int> mySet2 = new SortedSet<int>();

        // Inserting elements in SortedSet
        mySet2.Add(3);
        mySet2.Add(4);
        mySet2.Add(5);
        mySet2.Add(6);

        // Check if a SortedSet is a subset
        // of the specified collection
        // It should return false as SortedSet mySet2
        // is not a subset of SortedSet mySet1
        Console.WriteLine(mySet2.IsSubsetOf(mySortedSet));
    }
}
```

**Output:**

```cs
2
6
8
10
After Using Method
2
6
8
10
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . sorted set-1？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1?view=netframework-4.7.2)