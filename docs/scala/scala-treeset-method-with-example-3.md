# Scala TreeSet -()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-method-with-example-3/](https://www.geeksforgeeks.org/scala-treeset-method-with-example-3/)

在 Scala `TreeSet class`中， **-()** 方法被用来从给定的树集中移除元素。

> **方法定义:** def -(elem: A): TreeSet[A]
> 
> **返回类型:**它返回一个新的树集，其中一个元素从给定的树集中移除。

**示例#1:**

```scala
// Scala program of -() 
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
        val t1 = TreeSet("a", "e", "i", "o", "u") 

        // Print the TreeSet
        println(t1) 

        // Applying -() method  
        val result = t1 - ("u")

        // Display output 
        print("After removing an element: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
After removing an element: TreeSet(a, e, i, o)

```

**例 2:**

```scala
// Scala program of -() 
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
        val t1 = TreeSet(2, 1, 5, 4, 1, 3) 

        // Print the TreeSet
        println(t1) 

        // Applying -() method  
        val result = t1 - (1)

        // Display output 
        print("After removing an element: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
After removing an element: TreeSet(2, 3, 4, 5)

```