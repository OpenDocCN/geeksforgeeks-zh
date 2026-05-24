# Scala SortedSet init()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-init-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-init-method-with-example/)

**init()** 方法用于查找排序集合中除最后一个元素之外的所有元素。

> **方法定义:**定义初始化:排序集[A]
> 
> **返回类型:**返回除最后一个元素之外的 SortedSet 的所有元素。

**示例#1:**

```scala
// Scala program of init() 
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

        // Applying init method 
        val result = s1.init

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4)

```

**例 2:**

```scala
// Scala program of init() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(16, 22, 3, 41, 51) 

        // Applying init method 
        val result = s1.init

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(3, 16, 22, 41)

```