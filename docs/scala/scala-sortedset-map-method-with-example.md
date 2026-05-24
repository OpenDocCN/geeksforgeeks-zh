# Scala SortedSet map()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-map-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-map-method-with-example/)

通过将函数应用于排序集合的所有元素，使用 **map()** 方法来构建新的排序集合。

> **方法定义:** def 图【B】(f:(A)=>B):不可变。排序集
> 
> **返回类型:**应用给定函数后，返回包含所有元素的新 SortedSet。

**示例#1:**

```scala
// Scala program of map() 
// method 
import scala.collection.immutable.SortedSet 

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
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(5, 1, 3, 2, 4) 

        // Applying map method 
        val result = s1.map(x => x/2)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
TreeSet(0, 1, 2)

```