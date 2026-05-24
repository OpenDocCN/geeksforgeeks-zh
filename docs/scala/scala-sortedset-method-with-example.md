# Scala SortedSet -()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-method-with-example/)

-()方法用于创建一个新的排序集，并从排序集中移除给定的元素。

> **方法定义:** def -(elem: A): SortedSet[A]
> 
> **返回类型:**它返回一个新的排序集，给定的元素从排序集中移除。

**示例#1:**

```scala
// Scala program of -() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(4, 1, 5, 3, 2, 100) 

        // Applying -() method 
        val result = s1-(100)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)

```

**例 2:**

```scala
// Scala program of -() 
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

        // Applying -() method 
        val result = s1-(1)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
TreeSet(12, 23, 41, 43, 72)

```