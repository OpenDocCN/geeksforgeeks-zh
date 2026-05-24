# Scala 可变排序集图()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-map-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-map-method/)

在 Scala 可变集合中， **map()** 方法用于通过将函数应用于这个 SortedSet 的所有元素来构建一个新的 SortedSet。

> **方法定义:** def 图【B】(f:(A)=>B):可变。排序集
> 
> **返回类型:**应用给定函数后，返回包含所有元素的新 SortedSet。

**示例#1:**

```scala
// Scala program of map() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(5, 1, 3, 2, 4) 

        // Applying map method 
        val result = s1.map(x => x*x)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(1, 4, 9, 16, 25)

```

**例 2:**

```scala
// Scala program of map() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(5, 12, 3, 2, 4) 

        // Applying map method 
        val result = s1.map(x => x/2)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 6)

```