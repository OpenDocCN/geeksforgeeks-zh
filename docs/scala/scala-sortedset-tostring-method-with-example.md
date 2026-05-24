# Scala SortedSet toString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-tostring-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-tostring-method-with-example/)

**toString()** 方法用于返回由 SortedSet 的所有元素组成的字符串。

> **方法定义:** def toString(): String
> 
> **返回类型:**返回由 SortedSet 的所有元素组成的字符串。

**示例#1:**

```scala
// Scala program of toString() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 3, 4, 5) 

        // Applying toString method 
        val result = s1.toString

        // Display output
        println(result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)

```

**例 2:**

```scala
// Scala program of toString() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(41, 12, 23, 43, 1, 72) 

        // Applying toString method 
        val result = s1.toString

        // Display output
        println(result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 12, 23, 41, 43, 72)

```