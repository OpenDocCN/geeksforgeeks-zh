# Scala SortedSet min()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-min-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-min-method-with-example/)

min()方法用于查找所述列表中所有元素的最小元素。

> **方法定义:**定义最小值:A
> 
> **返回类型:**返回指定列表中所有元素中最小的一个。

**示例#1:**

```scala
// Scala program of min() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 3) 

        // Applying min method 
        val result = s1.min

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
1

```

**例 2:**

```scala
// Scala program of min() 
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

        // Applying min method 
        val result = s1.min

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
5

```