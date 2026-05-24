# Scala 可变排序集 toMap()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-tomap-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-tomap-method/)

在 Scala 可变集合中， **toMap()** 方法用于返回由 SortedSet 的所有元素组成的映射。

> **方法定义:** def toMap[T，U]: Map[T，U]
> 
> **返回类型:**它返回一个由 SortedSet 的所有元素组成的地图。

**示例#1:**

```scala
// Scala program of toMap() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet((1, 2), (3, 4), (5, 6)) 

        // Applying toMap method 
        val result = s1.toMap

        // Display output
        println(result)

    } 
} 
```

**Output:**

```scala
Map(1 -> 2, 3 -> 4, 5 -> 6)

```

**例 2:**

```scala
// Scala program of toMap() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet((12, 2), (13, 4), (15, 6)) 

        // Applying toMap method 
        val result = s1.toMap

        // Display output
        println(result)

    } 
} 
```

**Output:**

```scala
Map(12 -> 2, 13 -> 4, 15 -> 6)

```