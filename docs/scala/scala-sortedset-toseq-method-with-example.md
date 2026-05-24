# Scala SortedSet toSeq()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-toseq-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-toseq-method-with-example/)

**toSeq()** 方法用于返回由 SortedSet 的所有元素组成的序列。

> **方法定义:**def to eq:Seq[A]
> 
> **返回类型:**返回由 SortedSet 的所有元素组成的序列。

**示例#1:**

```scala
// Scala program of toSeq() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 3, 4, 5, 6) 

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
1
2
3
4
5
6

```

**例 2:**

```scala
// Scala program of toSeq() 
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
1
12
23
41
43
72

```