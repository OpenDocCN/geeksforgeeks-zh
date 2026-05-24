# Scala 不可变 TreeSet –()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-method-6/](https://www.geeksforgeeks.org/scala-immutable-treeset-method-6/)

在 Scala 不可变`TreeSet class`中，**–()**方法被用来从一个树集中减去另一个树集中的元素。

> **方法定义:**def –(即:IterableOnce[A]): TreeSet[A]
> 
> **返回类型:**它返回一个新的树集，该树集包含来自 A–B 树集的元素。

**示例#1:**

```scala
// Scala program of --() 
// method 

// Import TreeSet
import scala.collection.immutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSets
        val t1 = TreeSet("g", "e", "e", "k", "s") 

        val t2 = TreeSet("a", "e", "i", "o", "u")

        // Print the TreeSets
        println(t1) 

        println(t2)

        // Applying --() method  
        val result = t1 -- t2

        // Display output 
        print("Combined TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(e, g, k, s)
TreeSet(a, e, i, o, u)
Combined TreeSet: TreeSet(g, k, s)
```

**例 2:**

```scala
// Scala program of --() 
// method 

// Import TreeSet
import scala.collection.immutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSets
        val t1 = TreeSet(1, 6, 3, 2, 5) 

        val t2 = TreeSet(2, 1, 5, 4, 1)

        // Print the TreeSets
        println(t1) 

        println(t2)

        // Applying --() method  
        val result = t1 -- t2

        // Display output 
        print("Combined TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 5, 6)
TreeSet(1, 2, 4, 5)
Combined TreeSet: TreeSet(3, 6)
```