# Scala 可变排序集-()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-method-3/](https://www.geeksforgeeks.org/scala-mutable-sortedset-method-3/)

在 Scala 可变集合中，SortedSet -()方法用于创建一个新的 SortedSet，并从 SortedSet 中移除给定的元素。

> **方法定义:** def -(elem: A): SortedSet[A]
> 
> **返回类型:**它返回一个新的排序集，给定的元素从排序集中移除。

**示例#1:**

```scala
// Scala program of -() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(11, 55, 33, 20, 100) 

        // Applying -() method 
        val result = s1-(100)

        // Display output
        print(result) 

    } 
} 
```

**Output:**

```scala
TreeSet(11, 20, 33, 55)

```

**例 2:**

```scala
// Scala program of -() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(43, 23, 12, 41, 1) 

        // Applying -() method 
        val result = s1-(1)

        // Display output
        print(result) 

    } 
} 
```

**Output:**

```scala
TreeSet(12, 23, 41, 43)

```