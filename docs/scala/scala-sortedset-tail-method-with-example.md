# Scala SortedSet tail()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-tail-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-tail-method-with-example/)

**tail()** 方法用于返回一个 SortedSet，它包含除 SortedSet 的第一个元素之外的所有元素。

> **方法定义:**定义尾部:排序集[A]
> 
> **返回类型:**它返回一个 SortedSet，由除 SortedSet 的第一个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of tail() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(4, 1, 2, 3) 

        // Applying tail method 
        val result = s1.tail

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(2, 3, 4)

```

**例 2:**

```scala
// Scala program of tail() 
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

        // Applying tail method 
        val result = s1.tail

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(23, 41, 43)

```