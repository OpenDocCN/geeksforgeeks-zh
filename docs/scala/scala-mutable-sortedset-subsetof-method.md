# Scala 可变排序集 subsetOf()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-sub tof-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-subsetof-method/)

在 Scala 可变集合中，SortedSet**Substof()**方法用于测试一个 SortedSet 是否是另一个 SortedSet 的子 sorted set。

> **方法定义:**def subtof(即:SortedSet[A]):布尔值
> 
> **返回类型:**如果一个排序集是另一个排序集的子集，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of subsetOf() method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(4, 12, 2, 31) 

        val s2 = SortedSet(4, 12)

        // Applying subSortedSetOf method 
        val result = s2.subsetOf(s1)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of subsetOf() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(4, 12, 2, 31) 

        val s2 = SortedSet(4, 12)

        // Applying subSortedSetOf method 
        val result = s1.subsetOf(s2)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
false

```