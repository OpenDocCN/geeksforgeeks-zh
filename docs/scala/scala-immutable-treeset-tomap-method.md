# Scala 不可变 TreeSet toMap()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-tomap-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-tomap-method/)

在 Scala 不可变树集类中， **toMap()** 方法用于返回包含树集所有元素的映射。

> **方法定义:** def toMap[T，U]: Map[T，U]
> 
> **返回类型:**它返回一个由 TreeSet 的所有元素组成的地图。

**示例#1:**

```scala
// Scala program of toMap() 
// method 

// Import TreeSet
import scala.collection.immutable._

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
import scala.collection.immutable._

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