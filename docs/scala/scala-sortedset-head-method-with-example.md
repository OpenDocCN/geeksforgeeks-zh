# Scala SortedSet head()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-head-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-head-method-with-example/)

利用 **head()** 方法显示排序集的第一个元素。

> **方法定义:**定义标题:A
> 
> **返回类型:**返回 SortedSet 的第一个元素。

**示例#1:**

```scala
// Scala program of head() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(5, 1, 2, 3, 4) 

        // Applying head method 
        val result = s1.head

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
// Scala program of head() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(41, 16, 22, 3, 51) 

        // Applying head method 
        val result = s1.head

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
3

```