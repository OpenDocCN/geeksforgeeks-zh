# Scala TreeSet intersect()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-intersect-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-intersect-method-with-example/)

在 Scala `TreeSet class`中， **intersect()** 方法用于返回一个新的树集，该树集由给定树集中的元素组成。

> **方法定义:** def 交集【B】>:A】(即:集合。序列[B]):树集[A]
> 
> **返回类型:**它返回一个新的树集，该树集由给定树集中的元素组成。

**示例#1:**

```scala
// Scala program of intersect() 
// method 

// Import TreeSet
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSets
        val t1 = TreeSet(1, 3, 2, 7, 6, 5) 

        val t2 = TreeSet(11, 3, 12, 7, 16, 5) 

        // Print the TreeSets
        println("t1: " + t1)

        println("t2: " + t2)

        // Applying intersect() method  
        val result = t1.intersect(t2)

        // Displays output 
        println("TreeSet with common elements: " + result)

    } 
} 
```

**Output:**

```scala
t1: TreeSet(1, 2, 3, 5, 6, 7)
t2: TreeSet(3, 5, 7, 11, 12, 16)
TreeSet with common elements: TreeSet(3, 5, 7)

```

**例 2:**

```scala
// Scala program of intersect() 
// method 

// Import TreeSet
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSets
        val t1 = TreeSet(1, 3, 2, 7, 6, 5) 

        val t2 = TreeSet(1, 13, 2, 17, 16, 5) 

        // Print the TreeSets
        println("t1: " + t1)

        println("t2: " + t2)

        // Applying intersect() method  
        val result = t1.intersect(t2)

        // Displays output 
        println("TreeSet with common elements: " + result)

    } 
} 
```

**Output:**

```scala
t1: TreeSet(1, 2, 3, 5, 6, 7)
t2: TreeSet(1, 2, 5, 13, 16, 17)
TreeSet with common elements: TreeSet(1, 2, 5)

```