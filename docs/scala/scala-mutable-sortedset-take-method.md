# Scala 可变排序集取()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-take-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-take-method/)

在 Scala 可变集合中， **take()** 方法用于返回由 SortedSet 的前 n 个元素组成的 SortedSet。

> **方法定义:**def take(n:Int):sorted set[A]
> 其中“n”指定要选择的元素数量。
> 
> **返回类型:**它返回一个由 SortedSet 的前 n 个元素组成的 SortedSet。

**示例#1:**

```scala
// Scala program of take() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(11, 22, 33, 44) 

        // Applying take method 
        val result = s1.take(2) 

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(11, 22)

```

**例 2:**

```scala
// Scala program of take() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(4, 2, 3, 4) 

        // Applying take method 
        val result = s1.take(3) 

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(2, 3, 4)

```