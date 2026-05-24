# Scala SortedSet size()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-size-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-size-method-with-example/)

**size()** 方法用于查找排序集中的元素数量。

> **方法定义:**定义大小:整数
> 
> **返回类型:**返回排序集中的元素个数。

**示例#1:**

```scala
// Scala program of size() 
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

        // Applying size method 
        val result = s1.size

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
5

```

**例 2:**

```scala
// Scala program of size() 
// method 
import scala.collection.immutable.SortedSet

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 0) 

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