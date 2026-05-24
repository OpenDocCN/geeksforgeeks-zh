# Scala SortedSet toMap()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-tomap-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-tomap-method-with-example/)

利用 **toMap()** 方法返回由排序集的所有元素组成的地图。

> **方法定义:** def toMap[T，U]: Map[T，U]
> 
> **返回类型:**它返回一个由 SortedSet 的所有元素组成的地图。

**示例#1:**

```scala
// Scala program of toMap() 
// method 
import scala.collection.immutable.SortedSet 

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
import scala.collection.immutable.SortedSet 

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