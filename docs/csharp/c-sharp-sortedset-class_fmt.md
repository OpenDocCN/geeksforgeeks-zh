# C# |排序集合类

> 原文：[https://www.geeksforgeeks.org/c-sharp-sortedset-class/](https://www.geeksforgeeks.org/c-sharp-sortedset-class/)

`SortedSet`类表示按排序顺序排列的对象集合。这个类隶属于`System.Collections.Generic`命名空间。

## 特征

*   在C#中，`SortedSet`类可用于存储、移除或查看元素。
*   它保持升序，不存储重复的元素。
*   如果必须存储唯一元素并保持升序，建议使用`SortedSet`类。

## 构造器

| 构造器 | 描述 |
| :--- | :--- |
| `SortedSet()` | 初始化`SortedSet`类的新实例。 |
| `SortedSet(IComparer)` | 初始化使用指定比较器的`SortedSet`类的新实例。 |
| `SortedSet(IEnumerable)` | 初始化`SortedSet`类的新实例，该类包含从指定的可枚举集合中复制的元素。 |
| `SortedSet(IEnumerable, IComparer)` | 初始化`SortedSet`类的新实例，该类包含从指定的可枚举集合复制的元素，并使用指定的比较器。 |
| `SortedSet(SerializationInfo, StreamingContext)` | 初始化包含序列化数据的`SortedSet`类的新实例。 |

**示例：**

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

## 性能

| 属性 | 描述 |
| :--- | :--- |
| `Comparer` | 获取用于对排序集中的值进行排序的`IComparer`对象。 |
| `Count` | 获取排序集中的元素数量。 |
| `Max` | 获取`SortedSet`中由比较器定义的最大值。 |
| `Min` | 获取排序集中由比较器定义的最小值。 |

**示例：**

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

## 方法

| 方法 | 描述 |
| :--- | :--- |
| `Add(T)` | 将元素添加到集合中，并返回一个值，该值指示元素是否已成功添加。 |
| `Clear()` | 从集合中移除所有元素。 |
| `Contains(T)` | 确定集合是否包含特定元素。 |
| `CopyTo()` | 从目标数组的开头或指定的索引处开始，将`SortedSet<T>`的一部分或全部复制到兼容的一维数组中。 |
| `CreateSetComparer()` | 返回一个`IEqualityComparer`对象，该对象可用于创建包含单个集合的集合。 |
| `CreateSetComparer(IEqualityComparer)` | 根据指定的比较器返回一个`IEqualityComparer`对象，该对象可用于创建包含单个集合的集合。 |
| `Equals(Object)` | 确定指定的对象是否等于当前对象。 |
| `ExceptWith(IEnumerable)` | 从当前`SortedSet`对象中移除指定集合中的所有元素。 |
| `GetEnumerator()` | 返回遍历`SortedSet`的枚举数。 |
| `GetHashCode()` | 用作默认哈希函数。 |
| `GetObjectData(SerializationInfo, StreamingContext)` | 实现`ISerializable`接口并返回序列化`SortedSet`对象所必须的数据。 |
| `GetType()` | 获取当前实例的类型。 |
| `GetViewBetween(T, T)` | 返回排序集中子集的视图。 |
| `IntersectWith(IEnumerable)` | 修改当前的`SortedSet`对象，使其只包含也在指定集合中的元素。 |
| `IsProperSubsetOf(IEnumerable)` | 确定`SortedSet`对象是否是指定集合的适当子集。 |
| `IsProperSupersetOf(IEnumerable)` | 确定`SortedSet`对象是否是指定集合的适当超集。 |
| `IsSubsetOf(IEnumerable)` | 确定`SortedSet`对象是否是指定集合的子集。 |
| `IsSupersetOf(IEnumerable)` | 确定`SortedSet`对象是否是指定集合的超集。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `OnDeserialization(Object)` | 实现`ISerializable`接口，并在反序列化完成时引发反序列化事件。 |
| `Overlaps(IEnumerable)` | 确定当前`SortedSet`对象和指定的集合是否共享公共元素。 |
| `Remove(T)` | 从排序集中删除指定的项目。 |
| `RemoveWhere(Predicate)` | 从排序集中移除与指定谓词定义的条件匹配的所有元素。 |
| `Reverse()` | 返回一个`IEnumerable`，它以相反的顺序遍历`SortedSet`。 |
| `SetEquals(IEnumerable)` | 确定当前的`SortedSet`对象和指定的集合是否包含相同的元素。 |
| `SymmetricExceptWith(IEnumerable)` | 修改当前的`SortedSet`对象，使其只包含当前对象或指定集合中存在的元素，而不同时包含这两种元素。 |
| `ToString()` | 返回表示当前对象的字符串。 |
| `TryGetValue(T, T)` | 在集合中搜索给定值，并返回它找到的相等值（如果有）。 |
| `UnionWith(IEnumerable)` | 修改当前的`SortedSet`对象，使其包含当前对象或指定集合中存在的所有元素。 |

**示例：**

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

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1?view=netframework-4.7.2)