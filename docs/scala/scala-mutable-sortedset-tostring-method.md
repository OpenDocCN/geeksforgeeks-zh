# Scala 可变排序集 toString()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-tostring-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-tostring-method/)

在 Scala 可变集合中，SortedSet **toString()** 方法用于返回由 SortedSet 的所有元素组成的字符串。

> **方法定义:** def toString(): String
> 
> **返回类型:**返回由 SortedSet 的所有元素组成的字符串。

**示例#1:**

```scala
// Scala program of toString() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 3, 44, 5) 

        // Applying toString method 
        val result = s1.toString

        // Display output
        println(result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 3, 5, 44)

```

**例 2:**

```scala
// Scala program of toString() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(444, 555, 777, 666, 111) 

        // Applying toString method 
        val result = s1.toString

        // Display output
        println(result)

    } 
} 
```

**Output:**

```scala
TreeSet(111, 444, 555, 666, 777)

```