# Scala SortedSet max()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-max-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-max-method-with-example/)

利用 **max()** 方法寻找排序集中所有元素中最大的元素。

> **方法定义:** def 最大值:A
> 
> **返回类型:**返回排序集中所有元素中最大的一个。

**示例#1:**

```scala
// Scala program of max() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(5, 11, 23, 72, 14) 

        // Applying max method 
        val result = s1.max

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
72

```

**例 2:**

```scala
// Scala program of max() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(5, 11, 23, 72, 14, 21, 118) 

        // Applying max method 
        val result = s1.max

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
118

```