# Scala 可变 SortedSet subsetOf()方法

> 原文:[https://www . geesforgeks . org/Scala-mutable-sorted set-sub tof-method-2/](https://www.geeksforgeeks.org/scala-mutable-sortedset-subsetof-method-2/)

在 Scala 可变集合中，**Substof()**方法用于测试一个排序集是否是另一个排序集的子排序集。

> **方法定义:**子集(即:排序集[A]):布尔值
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