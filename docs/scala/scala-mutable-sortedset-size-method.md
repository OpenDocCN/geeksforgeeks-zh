# Scala 可变排序集大小()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-size-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-size-method/)

在 Scala 可变集合中，SortedSet **size()** 方法用于查找 SortedSet 中的元素数量。

> **方法定义:**定义大小:整数
> 
> **返回类型:**返回排序集中的元素个数。

**示例#1:**

```scala
// Scala program of size() 
// method 
import scala.collection.mutable.SortedSet

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(2, 5) 

        // Applying size method 
        val result = s1.size

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
2
```

**例 2:**

```scala
// Scala program of size() 
// method 
import scala.collection.mutable.SortedSet

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(2, 10, 115, 96, 36, 47, 458, 21) 

        // Applying size method 
        val result = s1.size

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
8

```