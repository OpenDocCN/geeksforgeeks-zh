# Scala 可变排序集计数()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-count-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-count-method/)

在 Scala 可变集合中， **count()** 方法用于计算 SortedSet 中的元素数量。

> **方法定义:** def 计数(p: (A) = >布尔值:Int
> 
> **返回类型:**返回排序集中存在的元素数量。

**示例#1:**

```scala
// Scala program of count()
// method
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating SortedSets 
        val s1 = SortedSet(10, 22, 32, 4, 5) 

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
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating SortedSets 
        val s1 = SortedSet(72, 666, 454) 

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