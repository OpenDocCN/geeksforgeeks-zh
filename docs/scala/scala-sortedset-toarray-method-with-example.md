# Scala SortedSet toArray()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-to array-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-toarray-method-with-example/)

**toArray()** 用于返回一个包含排序集所有元素的数组。

> **方法定义:**定义为数组:数组[A]
> 
> **返回类型:**它返回一个由 SortedSet 的所有元素组成的数组。

**示例#1:**

```scala
// Scala program of toArray() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 3, 4, 7) 

        // Applying toArray method 
        val result = s1.toArray

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
7

```

**例 2:**

```scala
// Scala program of toArray() 
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

        // Applying toArray method 
        val result = s1.toArray

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