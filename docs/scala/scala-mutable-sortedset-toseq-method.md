# Scala 可变排序集 toSeq()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-toseq-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-toseq-method/)

在 Scala 可变集合中，SortedSet **toSeq()** 方法用于返回由 SortedSet 的所有元素组成的序列。

> **方法定义:**def to eq:Seq[A]
> 
> **返回类型:**返回由 SortedSet 的所有元素组成的序列。

**示例#1:**

```scala
// Scala program of toSeq() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(11, 12, 13, 14) 

        // Applying toSeq method 
        val result = s1.toSeq

        // Display output
        for (ele <- result)
            println(ele)

    } 
} 
```

**Output:**

```scala
11
12
13
14

```

**例 2:**

```scala
// Scala program of toSeq() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(4, 2, 3, 43, 11, 72) 

        // Applying toSeq method 
        val result = s1.toSeq

        // Display output
        for (ele <- result)
            println(ele)

    } 
} 
```

**Output:**

```scala
2
3
4
11
43
72

```