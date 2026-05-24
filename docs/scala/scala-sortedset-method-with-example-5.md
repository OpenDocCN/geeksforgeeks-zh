# Scala SortedSet &()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-method-with-example-5/](https://www.geeksforgeeks.org/scala-sortedset-method-with-example-5/)

**& ()** 方法用于创建一个新的排序集，该排序集由给定排序集中的所有元素组成。

> **方法定义:**
> 
> **返回类型:**它返回一个新的排序集，该排序集由给定排序集中的所有元素组成。

**示例#1:**

```scala
// Scala program of &() method  
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(41, 12, 23, 43, 1, 72) 

        val s2 = SortedSet(1, 100, 5, 12, 23)

        // Applying &() method 
        val result = s1 & (s2)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
TreeSet(1, 12, 23)

```

**例 2:**

```scala
// Scala program of &() method  
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 3, 5, 7) 

        val s2 = SortedSet(2, 4, 6, 8)

        // Applying &() method 
        val result = s1 & (s2)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
TreeSet()

```