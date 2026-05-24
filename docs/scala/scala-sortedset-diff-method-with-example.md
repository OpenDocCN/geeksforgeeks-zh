# Scala SortedSet diff()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-diff-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-diff-method-with-example/)

**diff()** 方法用于计算排序集和另一排序集的差。

> **方法定义:**定义差异(即:排序集[A]):排序集[A]
> 
> **返回类型:**它返回一个 SortedSet，它是两个 sorted set 的差。

**示例#1:**

```scala
// Scala program of diff()
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

        val s2 = SortedSet(1, 2, 3)

        // Applying diff method 
        val s3 = s1.diff(s2) 

        // Displays output 
        for(elem <- s3)  
        println(elem) 

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
// Scala program of diff()
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

        val s2 = SortedSet(6, 2, 7, 8)

        // Applying diff method 
        val s3 = s1.diff(s2) 

        // Displays output 
        for(elem <- s3)  
        println(elem) 

    } 
} 
```

**Output:**

```scala
1
3
4
5

```