# Scala 可变排序集 toList()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-to list-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-tolist-method/)

在 Scala 可变集合中， **toList()** 方法用于返回由 SortedSet 的所有元素组成的列表。

> **方法定义:**定义为列表:列表[A]
> 
> **返回类型:**它返回一个由 SortedSet 的所有元素组成的列表。

**示例#1:**

```scala
// Scala program of toList() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(10, 20, 30, 40, 50) 

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
10
20
30
40
50

```

**例 2:**

```scala
// Scala program of toList() 
// method 
import scala.collection.mutable.SortedSet 

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