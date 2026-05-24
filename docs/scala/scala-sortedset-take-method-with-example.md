# Scala SortedSet take()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-take-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-take-method-with-example/)

**take()** 方法用于返回由 SortedSet 的前 n 个元素组成的 SortedSet。

> **方法定义:**def take(n:Int):sorted set[A]
> 其中“n”指定要选择的元素数量。
> 
> **返回类型:**它返回一个由 SortedSet 的前 n 个元素组成的 SortedSet。

**示例#1:**

```scala
// Scala program of take() 
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

        // Applying take method 
        val result = s1.take(2) 

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(1, 2)

```

**例 2:**

```scala
// Scala program of take() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(41, 12, 23, 43) 

        // Applying take method 
        val result = s1.take(3) 

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(12, 23, 41)

```