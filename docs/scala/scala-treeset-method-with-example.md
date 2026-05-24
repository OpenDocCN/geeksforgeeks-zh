# Scala TreeSet ++()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-method-with-example/)

在 Scala `TreeSet class`中， **++()** 方法用于将一个树集的元素添加到另一个树集。

> **方法定义:** def ++(即:IterableOnce[A]): TreeSet[A]
> 
> **返回类型:**它返回一个新的树集，该树集包含两个给定树集中的所有元素。

**示例#1:**

```scala
// Scala program of ++() 
// method 

// Import TreeSet
import scala.collection.mutable._

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

        // Applying ++() method  
        val result = t1 ++ t2

        // Display output 
        print("Combined TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(e, g, k, s)
TreeSet(a, e, i, o, u)
Combined TreeSet: TreeSet(a, e, g, i, k, o, s, u)

```

**例 2:**

```scala
// Scala program of ++() 
// method 

// Import TreeSet
import scala.collection.mutable._

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

        // Applying ++() method  
        val result = t1 ++ t2

        // Display output 
        print("Combined TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 5, 6)
TreeSet(1, 2, 4, 5)
Combined TreeSet: TreeSet(1, 2, 3, 4, 5, 6)

```