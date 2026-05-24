# Scala SortedSet count()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-count-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-count-method-with-example/)

**count()** 方法用于计算排序集中的元素数量。

> **方法定义:** def 计数(p: (A) = >布尔值:Int
> 
> **返回类型:**返回排序集中存在的元素数量。

**示例#1:**

```scala
// Scala program of count()
// method
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating SortedSets 
        val s1 = SortedSet(1, 2, 3, 4, 5) 

        // Applying count method 
        val result = s1.count(z=>true) 

        // Displays output 
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
// Scala program of count()
// method
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating SortedSets 
        val s1 = SortedSet(7, 6, 4) 

        // Applying count method 
        val result = s1.count(z=>true) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
3

```