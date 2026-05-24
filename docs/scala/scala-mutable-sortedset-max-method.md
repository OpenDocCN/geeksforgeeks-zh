# Scala 可变排序集 max()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-max-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-max-method/)

在 Scala 可变集合中，利用 **max()** 方法寻找 SortedSet 中所有元素中最大的元素。

> **方法定义:** def 最大值:A
> 
> **返回类型:**返回排序集中所有元素中最大的一个。

**示例#1:**

```scala
// Scala program of max() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 7, 4) 

        // Applying max method 
        val result = s1.max

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
7

```

**例 2:**

```scala
// Scala program of max() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(88, 54, 63, 458, 96) 

        // Applying max method 
        val result = s1.max

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
458

```