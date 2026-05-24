# Scala 可变排序集最后()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-last-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-last-method/)

在 Scala 可变集合中， **last()** 方法用于返回 SortedSet 的最后一个元素。

> **方法定义:**定义最后:答
> 
> **返回类型:**返回 SortedSet 的最后一个元素。

**示例#1:**

```scala
// Scala program of last() 
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

        // Applying last method 
        val result = s1.last

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
4

```

**例 2:**

```scala
// Scala program of last() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet("geeks", "for", "geeks", "classes") 

        // Applying last method 
        val result = s1.last

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
geeks

```