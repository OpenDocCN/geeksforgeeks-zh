# Scala SortedSet intersect()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-intersect-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-intersect-method-with-example/)

利用**交集()**方法计算两个排序集的交集。

> **方法定义:**定义交集(即:排序集[A]):排序集[A]
> 
> **返回类型:**它返回一个包含两个排序集中元素的排序集。

**示例#1:**

```scala
// Scala program of intersect() 
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

        val s2 = SortedSet(11, 12, 13, 4, 5) 

        // Applying intersect method 
        val s3 = s1.intersect(s2) 

        s3.foreach(x => println(x))
    } 
} 
```

**Output:**

```scala
4
5

```

**例 2:**

```scala
// Scala program of intersect() 
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

        val s2 = SortedSet(11, 2, 3, 4, 5) 

        // Applying intersect method 
        val s3 = s1.intersect(s2) 

        s3.foreach(x => println(x))
    } 
} 
```

**Output:**

```scala
2
3
4
5

```