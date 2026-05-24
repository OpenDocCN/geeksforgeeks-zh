# Scala SortedSet last()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-last-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-last-method-with-example/)

**last()** 方法用于返回 SortedSet 的最后一个元素。

> **方法定义:**定义最后:答
> 
> **返回类型:**返回 SortedSet 的最后一个元素。

**示例#1:**

```scala
// Scala program of last() 
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
import scala.collection.immutable.SortedSet 

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