# Scala 可变 SortedSet ++()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-method-4/](https://www.geeksforgeeks.org/scala-mutable-sortedset-method-4/)

在 Scala 可变集合中， **++()** 方法用于将一个 SortedSet 的元素添加到另一个 SortedSet。

> **方法定义:** def ++(elems: A): SortedSet[A]
> 
> **返回类型:**它返回一个包含两个排序集元素的新树集。

**示例#1:**

```scala
// Scala program of ++() method  
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 3, 5) 

        val s2 = SortedSet(2, 4, 6)

        // Applying ++() method 
        val result = s1 ++ s2

        // Display output
        print(result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5, 6)

```

**例 2:**

```scala
// Scala program of ++() method  
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(41, 12, 23, 43, 1, 72) 

        val s2 = SortedSet(1, 100, 5, 12, 23)

        // Applying ++() method 
        val result = s1 ++ s2

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
TreeSet(1, 5, 12, 23, 41, 43, 72, 100)

```