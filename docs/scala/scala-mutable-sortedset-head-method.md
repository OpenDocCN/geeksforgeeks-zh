# Scala 可变排序集头()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-head-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-head-method/)

在 Scala 可变集合中，SortedSet **head()** 方法用于显示 SortedSet 的第一个元素。

> **方法定义:**定义标题:A
> 
> **返回类型:**返回 SortedSet 的第一个元素。

**示例#1:**

```scala
// Scala program of head() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(12, 15, 14, 13) 

        // Applying head method 
        val result = s1.head

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
12

```

**例 2:**

```scala
// Scala program of head() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(6, 7, 5, 4, 1) 

        // Applying head method 
        val result = s1.head

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
1

```