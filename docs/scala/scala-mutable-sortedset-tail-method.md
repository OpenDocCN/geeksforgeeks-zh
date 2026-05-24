# Scala 可变排序集尾()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-tail-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-tail-method/)

在 Scala 可变集合中， **tail()** 方法用于返回一个 SortedSet，它由除 SortedSet 的第一个元素之外的所有元素组成。

> **方法定义:**定义尾部:排序集[A]
> 
> **返回类型:**它返回一个 SortedSet，由除 SortedSet 的第一个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of tail() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(8, 7, 6, 2) 

        // Applying tail method 
        val result = s1.tail

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(6, 7, 8)

```

**例 2:**

```scala
// Scala program of tail() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(4, 1, 23, 43) 

        // Applying tail method 
        val result = s1.tail

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(4, 23, 43)

```