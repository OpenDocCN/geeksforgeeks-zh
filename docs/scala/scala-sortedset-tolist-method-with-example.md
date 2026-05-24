# Scala SortedSet toList()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-to list-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-tolist-method-with-example/)

**toList()** 方法用于返回由 SortedSet 的所有元素组成的列表。

> **方法定义:**定义为列表:列表[A]
> 
> **返回类型:**它返回一个由 SortedSet 的所有元素组成的列表。

**示例#1:**

```scala
// Scala program of toList() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 3, 4, 5) 

        // Applying toList method 
        val result = s1.toList

        // Display output
        for (elem <- result)
            println(elem)

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

```

**例 2:**

```scala
// Scala program of toList() 
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

        // Applying toList method 
        val result = s1.toList

        // Display output
        for (elem <- result)
            println(elem)

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