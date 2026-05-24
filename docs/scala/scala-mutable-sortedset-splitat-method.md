# Scala 可变排序集 splitAt()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-splitat-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-splitat-method/)

在 Scala 可变集合中，使用 **splitAt()** 方法将给定的 SortedSet 在指定位置拆分成前缀/后缀对。

> **方法定义:**def splitAt(n:Int):(sorted set[A]，SortedSet[A])
> 其中，n 是我们需要拆分的位置。
> 
> **返回类型:**它返回一对由这个 SortedSet 的前 n 个元素和其他元素组成的树集。

**示例#1:**

```scala
// Scala program of splitAt() 
// method 
import scala.collection.mutable.SortedSet 

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
(TreeSet(2, 4), TreeSet(11, 31))

```

**例 2:**

```scala
// Scala program of splitAt() 
// method 
import scala.collection.mutable.SortedSet 

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