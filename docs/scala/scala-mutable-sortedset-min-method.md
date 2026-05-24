# Scala 可变排序最小()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-min-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-min-method/)

在 Scala 可变集合中，min()方法被用来寻找所述列表中所有元素的最小元素。

> **方法定义:**定义最小值:A
> 
> **返回类型:**返回指定列表中所有元素中最小的一个。

**示例#1:**

```scala
// Scala program of min() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(11, 22, 33) 

        // Applying min method 
        val result = s1.min

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
11

```

**例 2:**

```scala
// Scala program of min() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(11, 23, 72, 14, 21, 118) 

        // Applying min method 
        val result = s1.min

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
14

```