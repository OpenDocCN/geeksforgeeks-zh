# Scala SortedSet splitAt()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-splitat-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-splitat-method-with-example/)

**splitAt()** 方法用于在指定位置将给定的排序集拆分成前缀/后缀对。

> **方法定义:**def splitAt(n:Int):(sorted set[A]，SortedSet[A])
> 其中，n 是我们需要拆分的位置。
> 
> **返回类型:**它返回一对由这个 SortedSet 的前 n 个元素和其他元素组成的树集。

**示例#1:**

```scala
// Scala program of splitAt() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(2, 4, 11, 31) 

        // Applying splitAt method 
        val result = s1.splitAt(2)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
(TreeSet(2, 4), TreeSet(12, 31))

```

**例 2:**

```scala
// Scala program of splitAt() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 3, 4) 

        // Applying splitAt method 
        val result = s1.splitAt(2)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
(TreeSet(1, 2), TreeSet(3, 4))

```