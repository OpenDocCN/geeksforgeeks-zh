# Scala 可变排序集到数组()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-to array-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-toarray-method/)

在 Scala 可变集合中， **toArray()** 用于返回由 SortedSet 的所有元素组成的数组。

> **方法定义:**定义为数组:数组[A]
> 
> **返回类型:**它返回一个由 SortedSet 的所有元素组成的数组。

**示例#1:**

```scala
// Scala program of toArray() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(22, 3, 44, 77) 

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
3
22
44
77

```

**例 2:**

```scala
// Scala program of toArray() 
// method
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(443, 451, 772) 

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
443
451
772

```