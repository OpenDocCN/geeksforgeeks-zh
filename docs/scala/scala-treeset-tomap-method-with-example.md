# Scala TreeSet toMap()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-tomap-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-tomap-method-with-example/)

**toMap()** 方法用于返回由树集合的所有元素组成的地图。

> **方法定义:** def toMap[T，U]: Map[T，U]
> 
> **返回类型:**它返回一个由树集合的所有元素组成的地图。

**示例#1:**

```scala
// Scala program of toMap() 
// method 

// Import TreeSet
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet((1, 2), (3, 4), (5, 6))  

        // Print the TreeSet 
        println(t1) 

        // Applying toMap method  
        val result = t1.toMap

        // Display output 
        print("Elements in the Map: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet((1, 2), (3, 4), (5, 6))
Elements in the Map: Map(1 -> 2, 3 -> 4, 5 -> 6)

```

**例 2:**

```scala
// Scala program of toMap() 
// method 

// Import TreeSet
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet(("u", "a"), ("i", "o"), ("e", "f"))  

        // Print the TreeSet 
        println(t1) 

        // Applying toMap method  
        val result = t1.toMap

        // Display output 
        print("Elements in the Map: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet((e, f), (i, o), (u, a))
Elements in the Map: Map(e -> f, i -> o, u -> a)

```