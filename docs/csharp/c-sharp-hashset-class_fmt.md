# C# | HashSet Class

> 原文：[https://www.geeksforgeeks.org/c-sharp-hashset-class/](https://www.geeksforgeeks.org/c-sharp-hashset-class/)

`HashSet<T>` 是**独特元素**的无序集合。它属于 `System.Collections.Generic` 命名空间。它用于我们希望防止在集合中插入重复项的情况。就性能而言，与列表相比更好。

**HashSet 类的特征：**

*   `HashSet<T>` 类提供高性能的集合运算。集合是不包含重复元素的集合，其元素没有特定的顺序。
*   `HashSet<T>` 对象的容量是该对象可以容纳的元素数量。
*   当元素被添加到对象中时，对象的容量会自动增加。
*   `HashSet<T>` 集合未排序，不能包含重复元素。
*   `HashSet<T>` 提供了很多数学集合运算，比如集合加法（并集）和集合减法。

## 构造器

| 构造器 | 描述 |
| --- | --- |
| `HashSet()` | 初始化 `HashSet` 类的新实例，该实例为空，并使用集合类型的默认相等比较器。 |
| `HashSet(IEnumerable<T>)` | 初始化 `HashSet` 类的新实例，该实例使用集合类型的默认相等比较器，包含从指定集合复制的元素，并且具有足够的容量来容纳复制的元素数量。 |
| `HashSet(IEnumerable<T>, IEqualityComparer<T>)` | 初始化 `HashSet` 类的新实例，该实例使用集合类型的指定相等比较器，包含从指定集合复制的元素，并且具有足够的容量来容纳复制的元素数。 |
| `HashSet(IEqualityComparer<T>)` | 初始化 `HashSet` 类的新实例，该实例为空，并对集合类型使用指定的相等比较器。 |
| `HashSet(Int32)` | 初始化 `HashSet` 类的新实例，该实例为空，但为容量项保留了空间，并使用集合类型的默认相等比较器。 |
| `HashSet(Int32, IEqualityComparer<T>)` | 初始化 `HashSet` 类的新实例，该实例使用集合类型的指定相等比较器，并且具有足够的容量来容纳容量元素。 |
| `HashSet(SerializationInfo, StreamingContext)` | 用序列化数据初始化 `HashSet` 类的新实例。 |

**示例：**

```cs
// C# code to create a HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a HashSet of odd numbers
        HashSet<int> odd = new HashSet<int>();

        // Inserting elements in HashSet
        for (int i = 0; i < 5; i++) {
            odd.Add(2 * i + 1);
        }

        // Displaying the elements in the HashSet
        foreach(int i in odd)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出：**

```cs
1
3
5
7
9
```

## 性能

| 属性 | 描述 |
| --- | --- |
| `Comparer` | 获取用于确定集合中值的相等性的 `IEqualityComparer<T>` 对象。 |
| `Count` | 获取集合中包含的元素数量。 |

**示例：**

```cs
// C# code to get the number of
// elements that are contained in HashSet
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a HashSet of integers
        HashSet<int> mySet = new HashSet<int>();

        // Inserting elements in HashSet
        for (int i = 0; i < 5; i++) {
            mySet.Add(i * 2);
        }

        // To get the number of
        // elements that are contained in HashSet
        Console.WriteLine(mySet.Count);
    }
}
```

**输出：**

```cs
5
```

## 方法

| 方法 | 描述 |
| --- | --- |
| `Add(T)` | 将指定的元素添加到集合中。 |
| `Clear()` | 从 `HashSet` 对象中移除所有元素。 |
| `Contains(T)` | 确定 `HashSet` 对象是否包含指定的元素。 |
| `CopyTo(T[])` | 将 `HashSet` 集合的元素复制到数组中。 |
| `CreateSetComparer()` | 返回一个 `IEqualityComparer<T>` 对象，该对象可用于 `HashSet<T>` 对象的相等性测试。 |
| `Equals(Object)` | 确定指定的对象是否等于当前对象。 |
| `ExceptWith(IEnumerable<T>)` | 从当前 `HashSet` 对象中移除指定集合中的所有元素。 |
| `GetEnumerator()` | 返回遍历 `HashSet` 对象的枚举数。 |
| `GetHashCode()` | 用作默认哈希函数。 |
| `GetObjectData(SerializationInfo, StreamingContext)` | 实现 `ISerializable` 接口并返回序列化 `HashSet` 对象所需的数据。 |
| `GetType()` | 获取当前实例的类型。 |
| `IntersectWith(IEnumerable<T>)` | 修改当前 `HashSet` 对象，使其只包含该对象和指定集合中存在的元素。 |
| `IsProperSubsetOf(IEnumerable<T>)` | 确定 `HashSet` 对象是否是指定集合的适当子集。 |
| `IsProperSupersetOf(IEnumerable<T>)` | 确定 `HashSet` 对象是否是指定集合的适当超集。 |
| `IsSubsetOf(IEnumerable<T>)` | 确定 `HashSet` 对象是否是指定集合的子集。 |
| `IsSupersetOf(IEnumerable<T>)` | 确定 `HashSet` 对象是否是指定集合的超集。 |
| `MemberwiseClone()` | 创建当前对象的浅拷贝。 |
| `OnDeserialized(Object)` | 实现 `ISerializable` 接口，并在反序列化完成时引发反序列化事件。 |
| `Overlaps(IEnumerable<T>)` | 确定当前 `HashSet` 对象和指定的集合是否共享公共元素。 |
| `Remove(T)` | 从 `HashSet` 对象中移除指定的元素。 |
| `RemoveWhere(Predicate<T>)` | 从 `HashSet` 集合中移除与指定谓词定义的条件匹配的所有元素。 |
| `SetEquals(IEnumerable<T>)` | 确定 `HashSet` 对象和指定的集合是否包含相同的元素。 |
| `SymmetricExceptWith(IEnumerable<T>)` | 修改当前 `HashSet` 对象，使其只包含存在于该对象或指定集合中的元素，而不同时包含这两种元素。 |
| `ToString()` | 返回表示当前对象的字符串。 |
| `TrimExcess()` | 将 `HashSet` 对象的容量设置为它包含的元素的实际数量，向上舍入到附近的特定于实现的值。 |
| `TryGetValue(T, T)` | 在集合中搜索给定值，并返回它找到的相等值（如果有）。 |
| `UnionWith(IEnumerable<T>)` | 修改当前的 `HashSet` 对象，使其包含自身、指定集合或两者中存在的所有元素。 |

**示例：**

```cs
// C# code to Check if a HashSet is
// a subset of the specified collection
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a HashSet of integers
        HashSet<int> mySet1 = new HashSet<int>();

        // Inserting elements in HashSet
        // mySet1 only contains even numbers less than
        // equal to 10
        for (int i = 1; i <= 5; i++)
            mySet1.Add(2 * i);

        // Creating a HashSet of integers
        HashSet<int> mySet2 = new HashSet<int>();

        // Inserting elements in HashSet
        // mySet2 contains all numbers from 1 to 10
        for (int i = 1; i <= 10; i++)
            mySet2.Add(i);

        // Check if a HashSet mySet1 is a subset
        // of the HashSet mySet2
        Console.WriteLine(mySet1.IsSubsetOf(mySet2));
    }
}
```

**输出：**

```cs
True
```

**示例：**

```cs
// C# code to check if a HashSet
// contains the specified element
using System;
using System.Collections.Generic;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a HashSet of strings
        HashSet<string> mySet = new HashSet<string>();

        // Inserting elements in HashSet
        mySet.Add("DS");
        mySet.Add("C++");
        mySet.Add("Java");
        mySet.Add("JavaScript");

        // Check if a HashSet contains
        // the specified element
        if (mySet.Contains("Java"))
            Console.WriteLine("Required Element is present");
        else
            Console.WriteLine("Required Element is not present");
    }
}
```

**输出：**

```cs
Required Element is present
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.hashset-1?view=netframework-4.7.2)